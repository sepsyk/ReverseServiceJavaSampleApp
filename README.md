# Reverse service sample Java App

This webapp provides a service to reverse a message. The message needs to be send by HTTP POST to the service endpoint /reverse. The request body needs to contain the message in JSON format
{message: "This is a message!"}

The output will reverse the message string:
{"message":"!egassem a si sihT"}

Requirements:

Java 7
Maven 3

Steps to run the service:

1. Install prerequsites (Java, Maven)

2. Clone the sources from Github

3. Build the sources: mvn clean install

4. Run the service in an embedded Jetty container: mvn jetty:run

Alternatively, use the Dockerfile placed in the root to run the service in Docker.

Continuous Integration tests are done automatically by Travis CI, the Github integrated CI tool. The test procedure is described in .travis.yml file. Travis launches docker containers to test the maven build of the service, and runs JUnit tests. After that, integration tests are validating if the service is up and operating, by running simple curl based smoke tests against the container service endpoint.
