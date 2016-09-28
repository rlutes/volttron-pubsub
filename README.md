# README #

The PubSub and SynchronizedPubSub agents are VOLTTRON agents that include a number of convenience functions for subscribing to topics, handling topic matches, and synchronizing message exchange. Typically, these agents would not be run on the VOLTTRON platform as provided, but instead would be installed into the VOLTTRON virtual environment and extended by agents requiring this functionality.

## INSTALLATION ##

The following instructions assume you have already cloned this repository.

Make sure you have installed [VOLTTRON](https://github.com/VOLTTRON/volttron) and its dependencies.
Enable the VOLTTRON virtual environment
~~~
$ . [VOLTTRON repository location]/env/bin/activate
~~~
Install the package.
~~~
$ cd [volttron-pupsub repository location]
$ python setup.py install
~~~

## PACKAGING AND RUNNING ##

Navigate to VOLTTRON source directory
~~~
$ cd [VOLTTRON repository location]
~~~
Enable the VOLTTRON virtual environment
~~~
$ . env/bin/activate
~~~
Run VOLTTRON
~~~
$ volttron -vv -l [logfilepath.log] &
~~~
Export environment variables required for make-agent.sh
~~~
$ export SOURCE=[volttron-pupsub repository location]/pnnl/pubsubagent/
$ export CONFIG=[volttron-pupsub repository location]/pubsub
$ export TAG=pubsub-a
~~~
Run the VOLTTRON make-agent.sh script
~~~
$ . scripts/core/make-agent.sh
~~~
View the log. The agent will indicate that it has subscribed to the test/input topic.
~~~
$ tail -f [logfilepath.log]
~~~
~~~
...
2016-04-25 10:06:27,249 (pubsub-0.1 4493) pubsub.agent INFO: subscribed to test/input
...
~~~