If you want to apply as a soultion architect at [Datadog](http://datadog.com) you are in the right spot. Read on, it's fun, I promise.

<a href="http://www.flickr.com/photos/alq666/10125225186/" title="The view from our roofdeck">
<img src="http://farm6.staticflickr.com/5497/10125225186_825bfdb929.jpg" width="500" height="332" alt="_DSC4652"></a>

# The Challenge

Don't forget to read the **References**.

## Questions

### Level 1

* Sign up for Datadog, get the agent reporting metrics from your local machine. DONE
* Bonus question: what is the agent? 
The Agent has three main parts: the collector, dogstatsd, and the forwarder.
 The Agent is : The agent is severl process designed to do the following: 
The collector runs checks on the current machine for whatever integrations you have and it will capture system metrics like memory and CPU.
Dogstatsd is a statsd backend server you can send custom metrics to from an application.
The forwarder retrieves data from both dogstatsd and the collector and then queues it up to be sent to Datadog.


* Submit an event via the API?  I have submitted several events via the HTTP REST API and the Email Plain Text and Email JSON interfaces. 
* Get an event to appear in your email inbox (the email address you signed up for the account with)

### Level 2

* Take a simple web app ([in any of our supported languages](http://docs.datadoghq.com/libraries/)) that you've already built and instrument your code with dogstatsd. This will create **metrics**.
* While running a load test (see References) for a few minutes, visualize page views per second. Send us the link to this graph!
* Create a histogram to see the latency; also give us the link to the graph
* Bonus points if your simple app includes a database/webserver/cache we support, and you are able to enable their "integrations" in Datadog
* More bonus points for putting together more creative dashboards.

### Level 3

Using the same web app from level 2:
* tag your metrics with `support` (one tag for all metrics)
* tag your metrics per page (e.g. metrics generated on `/` can be tagged with `page:home`, `/page1` with  `page:page1`)
* visualize the latency by page on a graph (using stacked areas, with one color per `page`)

### Level 4

Same web app:
* count the overall number of page views using dogstatsd counters.
* count the number of page views, split by page (hint: use tags)
* visualize the results on a graph
* Bonus question: do you know why the graphs are very spiky?
 
### Level 5

Let's switch to the agent.

* Write an agent check that samples a random value. Call this new metric: `test.support.random`
* Visualize this new metric on Datadog, send us the link.

Here is a snippet that prints a random value in python:

```python
import random
print(random.random())
```

### Final in Person Interview
* Come to our office and do a Demo of Datadog 


## Instructions
If you have a question, create an issue in this repository.

To submit your answers:

1. Fork this repo.
2. Answer the questions in `answers.md`
3. Commit your code for question #4.
4. Submit a pull request.
5. Don't forget to include links to your dashboard(s)

## References

### How to get started with Datadog

* [Datadog overview](http://docs.datadoghq.com/overview/)
* [Guide to graphing in Datadog](http://docs.datadoghq.com/graphing/)

### The Datadog API and clients

* [API docs](http://docs.datadoghq.com/api)
* [Guide to the Agent](http://docs.datadoghq.com/guides/basic_agent_usage/)
* [Libraries](http://docs.datadoghq.com/libraries/)
* [Guide to Metrics](http://docs.datadoghq.com/guides/metrics/)

### Extending the Agent

* [Writing an agent check](http://docs.datadoghq.com/guides/agent_checks/)

### Tools you may need

Load testing
* [ab](https://httpd.apache.org/docs/2.2/programs/ab.html)
* [tsung](http://tsung.erlang-projects.org/user_manual.html#htoc2)
