Raven client for C#.

```
RavenClient ravenClient = new RavenClient(DSN_URL);
ravenClient.Logger = "C#";
ravenClient.LogScrubber = new Logging.LogScrubber();

// Capture exception with stacktrace.
try
{
	var i2 = 0;
	var i = 10 / i2;
}
catch (Exception e)
{
	ravenClient.CaptureEvent(e);
}

// Capture exception without stacktrace.
ravenClient.CaptureEvent(new Exception("Some crazy exception!"));
```