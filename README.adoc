= (Extremely) Basic Kafka Tutorial

This repository contains a super simple intro to Kafka tutorial.
You will learn how to do two things:

* Launch a Kafka broker locally using Docker
* Connect to that Kafka broker using the `kafka-python` library and write to and read from a topic.

== Getting Started

We're going to run a Docker compose template that launches 3 containers:

* broker - our Kafka broker
* zookeeper - used by Kafka for leader election
* jupyter - notebooks for connecting to our Kafka broker

Clone this repository:

[source, bash]
----
git clone git@github.com:mneedham/basic-kafka-tutorial.git && cd basic-kafka-tutorial
----

Open a terminal window and run the following command:

[source, bash]
----
docker-compose up
----

Near the beginning of the output you should see the following text:

```
jupyter-tutorial | [I 10:35:27.804 NotebookApp] The Jupyter Notebook is running at:
jupyter-tutorial | [I 10:35:27.804 NotebookApp] http://(4a031e4b5326 or 127.0.0.1):8888/?token=7907fef53948168308c829d48d9978b8f9c475b7c621c7d1
jupyter-tutorial | [I 10:35:27.804 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
jupyter-tutorial | [C 10:35:27.811 NotebookApp]
jupyter-tutorial |
jupyter-tutorial |     To access the notebook, open this file in a browser:
jupyter-tutorial |         file:///home/jovyan/.local/share/jupyter/runtime/nbserver-6-open.html
jupyter-tutorial |     Or copy and paste one of these URLs:
jupyter-tutorial |         http://(4a031e4b5326 or 127.0.0.1):8888/?token=7907fef53948168308c829d48d9978b8f9c475b7c621c7d1
```

Grab that URL and the token and open it in a web browser.
Given the above output we'd navigate to http://localhost:8888/?token=7907fef53948168308c829d48d9978b8f9c475b7c621c7d1, but you'll need to replace the token with your own one.

Once you've done that open `Kafka Tutorial.ipynb` and go through that.
The notebook installs a Python driver for Kafka, and then shows how to publish and consume a simple JSON message.

== Thanks

* The Docker Compose template is based on one shared with me by https://twitter.com/santand84[Andrea Santurbano^].
Andrea is the main author of https://github.com/neo4j-contrib/neo4j-streams[Neo4j Streams^], the Neo4j Kafka Integration.

* The producer and consumer code in the notebooks is adapted from Adnan Siddiqi's https://towardsdatascience.com/getting-started-with-apache-kafka-in-python-604b3250aa05[Getting started with Apache Kafka in Python article^] and https://github.com/kadnan/Calories-Alert-Kafka[accompanying repository^].
