# alpine-s3fs

Use [s3fs](https://github.com/s3fs-fuse/s3fs-fuse) with Alpine Linux to mount an S3 bucket as a directory in the filesystem.  
Uses environment variables to configure.

```shell
AWS_ACCESS_KEY_ID= # required unless IAM_ROLE is set
AWS_SECRET_ACCESS_KEY= # required unless IAM_ROLE is set
URL=https://s3.amazonaws.com # default, optional
S3_ACL=private # default, optional
S3_BUCKET=test-bucket # required
IAM_ROLE= # optional IAM role name, for usage on EC2.
```

## Versions:

1. `rjocoleman/alpine-s3fs:latest`

  This image is plain functionality on top of a standard [`alpine:3.3`](https://hub.docker.com/_/alpine/) image.

2. `rjocoleman/alpine-s3fs:ruby2`

  This image is based on the official [`ruby:2-alpine`](https://hub.docker.com/_/ruby/) image. It includes Ruby 2.x latest on top of Alpine 3.3.


## Usage

As a base image for a container. ENV `MOUNT_POINT` can be changed to direct the mount point to a different directory as required.

### Note

_Exporting_ Fuse based mounts as data volumes using the `--volumes-from` command doesn't work (this is a Docker thing).
