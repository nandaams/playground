# NOTES

### How to build

```cmd
docker build -t apache-server:v1.0 .
```

### How to run:

```cmd
docker run -d -t -p 8090:8088 --name my-apache-app apache-server:v1.0
```

// TBD: the importance of `-t`, without it, the container just exits few minutes after starting.

### Testing HTTPS

TBD

### A note on SSL Certificates

TBD

