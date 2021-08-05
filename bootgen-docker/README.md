# Installing BOOTBIN Docker Container

Use the following command to build the Docker container

```
$ docker build -t bootgen:latest .
```

Use the following command to run the Docker container

```
$ docker run -v ${PWD}:/workspace -it bootgen:latest
```
