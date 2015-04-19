
This docker container creates a local instance of dynamodb. It allows you to map the local dynamodb port and mount the storage to a particular directory (should be writable by other).

To run the container"

```
docker run --name <container-name> --rm -i -p <localport>:8000 -v <local-sys-mount-point>:/dynamodb/data eclecticlogic/dynamodb
```
