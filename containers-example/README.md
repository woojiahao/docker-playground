# Images
In Docker, images are like a machine image for your application. Inside the `Dockerfile`, instructions are given to "compile" your program. When `docker build` is used, Docker creates a file system similar to Linux and uses the instructions of the `Dockerfile` to construct the image.

This image is then uploaded to the Docker repository and when pulled by others, the entire filesystem or machine image is executed as is.

More information:
- [What is in a Docker image](https://cameronlonsdale.com/2018/11/26/whats-in-a-docker-image/)
- [`docker build` documentation](https://docs.docker.com/engine/reference/commandline/build/)
