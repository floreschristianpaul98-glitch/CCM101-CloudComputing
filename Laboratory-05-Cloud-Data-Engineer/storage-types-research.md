# Storage Types Research

Cloud storage can be organized into three major types: Block Storage, File Storage, and Object Storage. Each type uses a different way of organizing and accessing data.

| Storage Type | Description | Primary Use Case | Cloud Provider Example |
|---|---|---|---|
| **Block Storage** | Data is divided into fixed-size blocks and stored as separate blocks. The operating system or application manages the file system and organization of the blocks. | Virtual-machine disks, databases, and applications that need low-latency storage with direct access to storage volumes. | **AWS EBS (Elastic Block Store)** |
| **File Storage** | Data is organized into files and directories in a hierarchical file system. Multiple systems can access the shared file system through a network. | Shared folders, content management, home directories, and applications that require a traditional file system. | **AWS EFS (Elastic File System)** |
| **Object Storage** | Data is stored as objects together with metadata and a unique identifier. Objects are organized inside containers called buckets. | Large amounts of unstructured data such as photos, videos, backups, documents, and logs. | **AWS S3 (Simple Storage Service)** |

### Why Object Storage for User-Uploaded Images?

Object Storage is well suited to the client's photo-sharing application because it is designed for large amounts of unstructured data such as images and can organize objects in buckets. It also separates stored objects from the web-server container, which is important because containers are ephemeral and should not be relied on as permanent storage.
