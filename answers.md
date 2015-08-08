One of the key and maybe the most powerful features of #DataDog is that it is the first APM Solution that support #MetaData across the entire solution. DataDog is the King of #MetaAPM.  

What does that really mean:

You can capture EVERYTHING about your application in DataDog with respective to Performnace, Availibility, Business Success.



Sign up for Datadog, get the agent reporting metrics from your local machine. DONE
Bonus question: what is the agent? The Agent is : is the primary means for pushing metrics and events into DataDog.  It is made up of three parts: Collector, Forwarder and dogstatsd. 

Submit an event via the API? I have submitted several events via the HTTP REST API and the Email Plain Text and Email JSON interfaces.
Get an event to appear in your email inbox (the email address you signed up for the account with)



Your answers to the questions go here.
Examples:

@support – this will reach Datadog support directly when posted in your stream.
@all – this will send a notification to all members of your organization.
@yourname – this will notify the specific user named ‘yourname’.
@test@test.com this will send an email to test@test.com.

Using aggregration key to link multiple events.   
This can be a nice use for correlation.  
Ingrations with AppDynamics could use the Transaction ID to reference multiple Snapshots. 

Created a Docker instance. 

https://hub.docker.com/r/tutum/wordpress/
Installed https://github.com/tutumcloud/lamp/blob/master/Dockerfile

Directly Edited vi /opt/datadog-agent/agent/config.py to get rid of the syslog configuration errors.  
The error message for system may have something to do with the way Docker handles network sockets. 


http://help.datadoghq.com/hc/en-us/requests/31252



Updated Wordpress Docker to include DataDog Agent:


# Updated Dockerfile 

FROM tutum/lamp:latest
MAINTAINER Fernando Mayo <fernando@tutum.co>, Feng Honglin <hfeng@tutum.co>

# Install plugins
RUN apt-get update && \
  apt-get -y install php5-gd && \
  rm -rf /var/lib/apt/lists/*

RUN apt-get -qq update
RUN apt-get -qq -y install curl 
# Download latest version of Wordpress into /app
RUN rm -fr /app && git clone --depth=1 https://github.com/WordPress/WordPress.git /app

# Configure Wordpress to connect to local DB
ADD wp-config.php /app/wp-config.php

# Modify permissions to allow plugin upload
RUN chown -R www-data:www-data /app/wp-content /var/www/html
# Add database setup script
ADD create_mysql_admin_user.sh /create_mysql_admin_user.sh
ADD create_db.sh /create_db.sh
RUN chmod +x /*.sh
# use DataDog Agent
RUN DD_API_KEY=55f5cd3bfc0fd6a0710c7423da543e10 bash -c "$(curl -L https://raw.githubusercontent.com/DataDog/dd-agent/master/packaging/datadog-agent/source/install_agent.sh)"
EXPOSE 80 3306
CMD ["/run.sh"]

