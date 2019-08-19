# Services
Services refer to different pieces of an application within a distributed application. For instance, a video sharing site will have a service for storing application data in a database, a service for video transcoding in the background after a user uploads something, a service for the front-end and so on.

In terms of Docker, services are just "containers in production". A service runs one image, but it codifies the way that image should run - what ports to use, how many replicas of the container should run so the service has the capacity it needs, etc. Scaling a service changes the number of container instances running that piece of software, assigning more computing resources to the service in the process.
