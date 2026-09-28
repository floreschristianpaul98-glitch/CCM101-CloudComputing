# MinIO Deployment

## Deployment Overview

MinIO is an open-source, S3-compatible object storage server. In this laboratory, it is deployed as a Docker container in the KillerCoda Ubuntu Playground.

## 1. Docker Deployment Command

The exact command provided in the laboratory activity is:

```bash
docker run -d -p 9000:9000 -p 9001:9001 --name minio-server \
-e "MINIO_ROOT_USER=cloudadmin" \
-e "MINIO_ROOT_PASSWORD=CloudNova2026!" \
elestio/minio server /data --console-address ":9001"
```

### Command Breakdown

- `docker run -d` — creates and starts the container in detached mode.
- `-p 9000:9000` — maps the MinIO API port from the container to the host.
- `-p 9001:9001` — maps the MinIO Web Console port from the container to the host.
- `--name minio-server` — gives the container the name `minio-server`.
- `elestio/minio` — specifies the MinIO Docker image.
- `server /data` — starts MinIO in server mode using `/data` for object storage.
- `--console-address ":9001"` — tells MinIO to make its Web Console available on port 9001.

## 2. Environment Variables

The `-e` flags define environment variables inside the container:

- `MINIO_ROOT_USER=cloudadmin` sets the MinIO root/administrator username.
- `MINIO_ROOT_PASSWORD=CloudNova2026!` sets the MinIO root/administrator password.

These variables provide the credentials used to sign in to the MinIO Web Console.

> **Security note:** The password above is the credential specified by the laboratory handout. In a real production environment, credentials should be managed securely and should not be committed to a public GitHub repository.

## 3. Verify the Container

After starting MinIO, verify that the container is running:

```bash
docker ps
```

The running container should appear with the name:

```text
minio-server
```

## 4. Access the Web Console

In KillerCoda, open the **Traffic / Ports** or **Custom Ports** interface and access port:

```text
9001
```

Log in using the credentials specified in the Docker command.

## 5. Create the Bucket

In the MinIO Web Console:

1. Open **Buckets**.
2. Select **Create Bucket**.
3. Enter the bucket name:

```text
client-photos
```

4. Save/create the bucket.

## 6. Upload a Test Object

Open the `client-photos` bucket and use **Upload** to upload a safe sample image or text file.

## 7. Required Evidence

Add the following screenshots to the `screenshots/` directory:

- `minio-deployed.png` — terminal evidence showing successful deployment and the running container.
- `minio-bucket-upload.png` — MinIO Web Console evidence showing the `client-photos` bucket and uploaded object.

## Lab Values

| Item | Value |
|---|---|
| MinIO container | `minio-server` |
| API port | `9000` |
| Web Console port | `9001` |
| Root user | `cloudadmin` |
| Bucket | `client-photos` |
| Docker image | `minio/minio` |
