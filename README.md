# docker-binder
Add a temporary bind mount to a running container

This simple script will create a bind mount from your host into a running docker container, in case you forgot to
add a volume and docker cp isn't good enough.

```
binder <CONTAINER> <HOST_DIR> <CONTAINER_DIR>
binder [-u | -d] <CONTAINER> <CONTAINER_DIR>
Add/remove a temporary bind mount in a container

  -u              remove (unmount) the mount instead of adding it
  -d              remote the mount and delete the container dir. This may delete container data!
  CONTAINER       the name or ID of the container to add the bind mount to
  HOST_DIR        the path of the host directory to mount
  CONTAINER_DIR   the path inside the container for the mount
```

Run the script with container, host_dir, container_dir to create a mount. Run the script with -u and the same 3 args to
remove that mount. You can substitute -d instead of -u to have it clean up the mount dir as well.

If you mount over an existing container directory, and then remove the mount with the -d option, it will delete the
pre-existing container directory!
