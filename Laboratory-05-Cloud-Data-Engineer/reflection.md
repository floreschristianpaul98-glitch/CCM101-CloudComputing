# Mission Reflection

## 1. Why is object storage better suited for storing millions of photos compared to a traditional block storage hard drive?

Object storage is well suited for millions of photos because photos are unstructured data and can be stored as individual objects with metadata and unique identifiers. Instead of depending on a traditional file-system hierarchy or a block-storage volume, the application can place large numbers of objects into a bucket. This model is appropriate for a photo-sharing application because the images are independent objects that can be uploaded and accessed separately. Object storage also keeps the data separate from the web-server container, which is important because containers are temporary and can be replaced.

## 2. How did using Docker make it easier to deploy the MinIO storage server?

Docker made the deployment easier because MinIO could be started from an existing container image with one command. There was no need to manually install and configure all of the server software on the Ubuntu environment. The command also made the configuration clear by mapping ports, setting the container name, and providing the administrator credentials through environment variables. This makes the deployment repeatable and easier to manage.

## 3. What is a "bucket" in the context of cloud storage?

A bucket is a container used by object storage to organize and hold objects. In this laboratory, the bucket is named `client-photos`, and the uploaded test image or text file is stored inside it. The bucket provides a logical place where the application's objects can be managed.

## 4. How do you think large enterprise companies ensure their object storage data is not lost if the physical server crashes?

Large enterprise systems can reduce the risk of data loss by maintaining redundant copies of data and distributing storage across multiple physical devices or locations. They can also use replication, backups, monitoring, and recovery procedures. If one physical server fails, redundant storage can allow the data to remain available or be restored. The exact protection method depends on the storage platform and its configuration.

## 5. How is your confidence in navigating the Linux command line growing?

This activity helps build confidence because it requires using the Linux terminal to run a Docker command and verify a running container. Commands such as `docker run` and `docker ps` provide direct control over the cloud service. Repeating these steps makes it easier to understand how command-line tools are used to deploy and inspect services. The experience also shows how Linux, Docker, and cloud services work together in a practical environment.

## Overall Reflection

The mission connected cloud-storage concepts with a practical deployment. I learned that Block, File, and Object Storage are designed for different workloads, and that Object Storage is particularly appropriate for large collections of images. Deploying MinIO with Docker also demonstrated how containerization can simplify the setup of a cloud service. Creating the `client-photos` bucket and uploading an object made the concept of a bucket more concrete. Overall, the activity strengthened my understanding of object storage, Docker deployment, web-console access, and Linux command-line operations.
