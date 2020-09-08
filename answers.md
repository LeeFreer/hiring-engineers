
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
### Operating System
Whether you're a master of Microsoft Operating Systems, a Linux Ninja, or a Mac OS Wizard; or you've containerized your application (look at you, seriously) Datadog has you covered; 
sign up for a free Datadog account, click on Integrations > Agent, download your agent and get ready to ingest.

### Tagging
As part of our setup, we'll want to use Tags in our Agent config file. Think of tags asa way of adding dimensions to Datadog telemetries so they can be filtered, aggregated, and
compared in Datadog visualizations. Start your agent once you've added your tags to the Agent config file, and see the new host in Datadog Console.

### Databases
But what if I want to monitor Databases? 
Datadog has well over 400 [supported integrations](https://docs.datadoghq.com/integrations/)
Make sure to edit the correct configuration file (conf.yaml) like I've done below, in my particular case I'd like to monitor a postgreSQL database on my Windows Development Desktop.

## Custom Checks
What about custom Agent checks? Those aren't really supported integrations...
Actually, they are. As long as the check is written on a supported language (think Go, NodeJS, Python, etc). I have written a short script that randomly outputs a number, between 0 and 9999.
In order to create a custom Agent check, you'll need 2 files:

    1. Conf file
    2. Script file

![Pro Tip](https://u.cdn.sera.to/content/images/93/23193/23193.png) Did you know?
Did you know you can change the collection interval without modifying script check files you created?
Go here, do this, and do that...

## Visualizing Data & Datadog API
Let's talk about the [Datadog API](https://docs.datadoghq.com/api/) and timeboards with metrics; as you can see below I created the dashboard "Hello Datadog Dashboard" using Postman.
[Postman](https://www.postman.com/) is a software development tool that enables us to test calls to APIs, in this particular case I've configured it to use my account and sent the following payloads:

### Payload 1:
### Payload 2:
### Payload 3:

Now that we've created our dashboard from Postman via API calls, let's see how it looks:

We can see the CMetric's average, our rollup and any associated anomoly's, very cool indeed.

![Pro Tip](https://u.cdn.sera.to/content/images/93/23193/23193.png) Did you know?
Anomolies give you a historical trend for metrics, when a metric is outside of the threshold, the line becomes red.
This shows that the metric is behaving outside of the "normal" historical range; Can you think of any use cases?

## Monitoring Data
WIP
