# High Performance Dynamic Web Mapping with CartoDB Test

This repo contains the information and code to perform a test of heavy load of a web dynamic map provided by CartoDB.

The test simulates 15,000 QPS by using JMeter on Google Cloud Platform. It simulates a user session of a test map displaying 15,000 features that are updated every 10 seconds. 

The goal is to demonstrate high frequency updates on the map, every 10 seconds, with a heavy load of visits to it, 15,000 requests per second.

To perform this test different components have been created

## The testing map and data

Available at ...

The map represent the status of roads in Texas. Each feature has a field of "status" that is used to render a different icon.

In total there are 15,000 road segments on the database.

A dump of the table can be downloaded here.

## Updating the data

A simple Python script is resposible for updating the data every 10 seconds on CartoDB.

## The CartoDB Server

We are running on a CartoDB on Google Cloud Platform Enterprise server. It has 28GB of dedicated memory and 200GB of storage. 

## JMeter

To create a user simulation and perform multiple requests as same time we are using JMeter. In JMeter you define an experiment and then launch it on many different instances.

We base our test on this documentation created by Google.

## Google Cloud Computing Engine

We are using 12 n1-standard Google Cloud instances. Each of them is able to reproduce 600 QPS to the CartoDB Servers.

## Results

The results had been discussed on this white paper. We demonstrate ability of CartoDB to handle more traffic than the testing servers can handle.

Here is a video result:


Here are some graphs of the running process.


## Credits

Thanks to AppGeo and Google for the resources provided.
