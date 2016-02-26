# Test Varnish VCL

This is a way to test VCL changes locally, with the help of Docker.

## Installation

[Install Docker](https://docs.docker.com/engine/installation/).

[Install Docker compose](https://docs.docker.com/compose/install/).

## Running

Build the docker images

`docker-compose build`

Run the docker images

`docker-compose up`

## What did that do?

You're now running a container with Varnish that is connected to a node.js back-end. You should be able to visit `http://{docker Machine IP}` in your browser to hit Varnish.

## Testing your Varnish VCL

Drop your Varnish VCL into `varnish/default.vcl`, rebuild the docker images and run them.

The Dockerfile (`varnish/Dockerfile`) includes the Querystring VMOD. You can modify this Dockerfile to match your Varnish instance (e.g. adding other vmods, or whatever else you did to your Varnish server).

Just make sure to leave the `backend` block in `varnish/default.vcl` alone, as that provides connectivity to the node instance.
