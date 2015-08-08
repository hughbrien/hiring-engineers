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


Forked Wordpress Docker and updated the Container Dockerfile. 
https://github.com/hughbrien/wordpress

