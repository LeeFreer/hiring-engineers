
# Data Visualization: Datadog's North Star :star:
## Always see the horizon
![North Star](http://cdn.lowgif.com/full/4c0f211082b1edb6-.gif)

Building a successful business is not about climbing ladders, or fending off competition in a particular space; it's about building momentum and continuing to move forward.
When a business grows, "Growing pains" are more than just obstacles or obstructions, sometimes you find yourself not moving as much as you'd like to. 
You've lost sight of that horizon, and that's really what I'm here to talk about today.

Datadog's way to keep the visual open through visualization of metrics, traces and logs in one integrated platform are the most effective way to always see the horizon; collecting data
from hundred of technologies for visualization, troubleshooting, machine learning, alerting and more, keep the visual open. Don't lose your way.
Never lose sight of the direction you want to go. Don't get lost in a troubleshooting sea, look up to the north star for direction.

Let's go over dig deeper how Data-dog works, how simple and fast it is to get started:

## Easy Setup
### :computer: Operating System 
Whether you're a master of Microsoft Operating Systems, a Linux Ninja, or a Mac OS Wizard; or you've containerized your application (look at you, seriously) Datadog has you covered. Sign up for a free Datadog account, click on Integrations > Agent, download your agent and get ready to ingest.

Once the Agent is installed, you'll be able to access the Datadog Agent Manager (or DAM) on (Windows/MacOS) by visiting it's default location http://127.0.0.1:5002

![WindowsPCDatadogAgent](https://i.imgur.com/ZCVWw2Z.png)

:high_brightness: Pro Tip:
DAM allows you to review the Agent's Status, look at Logs, review Settings, reach out to Support by using Flare and Restart the Agent after making any configuration change. Super Helpful  :thumbsup:

### Tagging
As part of our setup, we'll want to use Tags in our Agent config file. Think of tags as a way of adding dimensions to Datadog telemetries so they can be filtered, aggregated, and compared in Datadog visualizations. 

We'll find the Agent config file (in my particular case, again, using Windows) in C:\ProgramData\Datadog\datadog.yaml

```
...
syslog_key: ""
syslog_pem: ""
syslog_rfc: false
syslog_tls_verify: true
syslog_uri: ""
tag_value_split_separator: {}
tags: [ "env:dev", "os:win10pro", "location:columbia"]
telemetry:
  enabled: true
tracemalloc_blacklist: ""
tracemalloc_debug: false
tracemalloc_whitelist: ""
use_dogstatsd: true 
...
```
I have added 3 tags, ENV for Environment, OS for Operating System, and location for... well you guessed it, location. "columbia" works for me as it's the street where I live.

:point_up: Don't forget to restart your agent once you've added your tags to the Agent config file, and see the new host in Datadog Console.

### conf.d 
Now that we have the Agent running, we can really start to customize our Agent. Navigate to C:\ProgramData\Datadog\conf.d\ and here you'll find all the out-of-the-box integrations Datadog can talk to. Let's say you want to monitor Apache, boom open apache.d/ or maybe a connection to nagios, get in that nagios.d/ folder. The world is your oyster (or at least your Datadog directory is).

Every folder has a corresponding conf.yaml.example to get you started, just make sure you create a conf.yaml per each configuration on it's corresponding folder, edit the values for each integration and restart your Agent. 

Let's go over a few integrations I need to setup :smirk:

### Databases
But what if I want to monitor Databases? I hear you saying out loud :bowtie:

Funny you asked, that's EXACTLY what I needed to configure next... By the way, Datadog has well over 400 [supported integrations](https://docs.datadoghq.com/integrations/) and each integration has detailed instructions, I recommend you browse through and see what you can take advantage of

:point_up:Remember, make sure to edit the correct configuration file (conf.yaml) like I've done below, in my particular case I needed to monitor a postgreSQL database on my Windows Development Desktop.

![PostgreSQLConf](https://i.imgur.com/7FuMCKn.png)
I created the conf.yaml, following the instructions from Datadog's integration page. Easy Peasy.

## Custom Checks
You: Well... what about scripts Luis? What if I wrote a script and I wanted the result to be shipped to Datadog uh?!

Me:  I know, I know exactly what you're saying, this is getting a little weird..

As long as the check is written on a supported language (think Go, NodeJS, Python, etc), you won't have any problems.
In fact, I have written a short script that randomly outputs a number, between 0 and 10000, in python.
In order to create a custom Agent check, you'll need the following:

    1. Conf file
    2. Script file

:high_brightness: Pro Tip:
Did you know you can change the collection interval without modifying script check files you created?
Go here, do this, and do that...

## DAM DAM DAM
Let's go back to DAM, restart the Agent and take a look at Status > Collector


![DAM PGSQL](https://i.imgur.com/bUWSh9y.png)
![DAM CMetrics](https://i.imgur.com/5B5PJz9.png)


I see that cmetrics & postgres are good to go! This means we should expect Datadog Console to have this data available for use!


![Datadog Console shows PGSQL & CMetrics](https://i.imgur.com/GW7MHVp.png)

And we are good to go! :hand:

## Visualizing Data & Datadog API
Let's pivot and talk about the [Datadog API](https://docs.datadoghq.com/api/), timeboards with metrics; as you can see below I created the dashboard "Hello Datadog Dashboard" using Postman.

[Postman](https://www.postman.com/) is a software development tool that enables us to test calls to APIs, in this particular case I've configured it to use my account and sent the following payloads:

### Payload 1:
### Payload 2:
### Payload 3:

Now that we've created our dashboard from Postman via API calls, let's see how it looks:

We can see the CMetric's average, our rollup and any associated anomoly's, very cool indeed.

:high_brightness: Pro Tip:
Anomolies give you a historical trend for metrics, when a metric is outside of the threshold, the line becomes red.
This shows that the metric is behaving outside of the "normal" historical range; Can you think of any use cases?

## Monitoring Data
WIP
