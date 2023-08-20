# jetson-nano-gpu-pod
Docker image build for runing GPU workloads on Jetson Nano - based on the NVIDA image: nvcr.io/nvidia/l4t-base:35.4.1


To build a Docker image and then upload (push) it to Docker Hub, follow the steps below. 

1.  **Navigate to Your Project Directory**

Make sure you're in the directory containing your `Dockerfile`.

```
bashcd /path/to/your/project/

```

2.  **Build the Docker Image**

Replace `<image_name>` with a name for your Docker image and `<tag>` with a tag (often `latest` is used for the most recent version).

```
bashdocker build -t <image_name>:<tag> .

```

For example:

```
bashdocker build -t myapp:latest .

```

3.  **Log in to Docker Hub**

If you aren’t already logged in, you'll need to log in to Docker Hub from the command line:

You'll be prompted to enter your Docker Hub username and password.

4.  **Tag Your Image for Docker Hub**

Before you can push your image to Docker Hub, you need to tag it with your Docker Hub username and repository name.

Replace `<dockerhub_username>`, `<repository_name>`, `<image_name>`, and `<tag>` with appropriate values.

```
bashdocker tag <image_name>:<tag> <dockerhub_username>/<repository_name>:<tag>

```

For example, if your Docker Hub username is `johndoe` and you want the repository name to be `myapp`:

```
bashdocker tag myapp:latest johndoe/myapp:latest

```

5.  **Push the Docker Image to Docker Hub**

Now, you can push the image to Docker Hub using the following command:

```
bashdocker push <dockerhub_username>/<repository_name>:<tag>

```

Using the above example:

```
bashdocker push johndoe/myapp:latest

```

6.  **Logout from Docker Hub (Optional)**

For security reasons, you might want to log out from Docker Hub after pushing your image:

That's it! Your image should now be available on Docker Hub, and you (or anyone else) can pull it from any system with Docker installed using the command `docker pull <dockerhub_username>/<repository_name>:<tag>`.