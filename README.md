# mqtt-lirc

A simple MQTT agent based on node.js that subscribes to a given list of MQTT topics
on the specified broker and executes a lirc command whenever
a message arrives. It can also be used in combination with an Home Automation Framework like [Home.Pi](https://github.com/denschu/home.pi)

## Setup

	npm install --production

## Start Broker

	mosquitto
	
## Publish Configuration

	mosquitto_pub -d -r -t home/devices/appletv/config/command/on  -m "XYZ"
	
##Start Binding with Topics to subscribe

	node mqtt-exec -t home/devices/appletv/state/set

## Execute command

	mosquitto_pub -d -t home/devices/appletv/state/set -m "on"

## dependencies

* [mqtt.js](http://github.com/adamvr/MQTT.js)
* [optimist](http://github.com/substack/node-optimist)

