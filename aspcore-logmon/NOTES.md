## Quick Notes

This is a test ASP.NET 6 app that has HTTP logging turned on, to test the [LogMonitor](https://github.com/microsoft/windows-container-tools/tree/main/LogMonitor) tool. It's unofficial binary is put in the [`/bin`](./bin) directory, but you can rebuild the latest and update.

To build the image, from this directory, run:

> You can use your own preferred in the place of `asplogmon`, `asplogmon_app` and port `5050`.

```
docker build -t asplogmon .
```

Then run the container with:

```
docker run -d -p 5050:80 --name asplogmon_app asplogmon
```

Check the run the ASP web app from `localhost:5050` and check the logs.
