# Port Forwarding

When developing web applications on a remote
server that is not available on the internet,
say on localhost:3000, you can still access that
web application locally with the magic of
port forwarding!

You can do this on OSX and on Windows (with Putty).

Say you wanted to view a web app on your local machine to port `3333`
which is running on a remote VM on port `3000`, you could use the
following syntax on OSX in the terminal to bind the remote `3000` to your
local `3333`:

```sh
ssh -fNL 3333:localhsot:3000 user@remote_server
```

The key flags here are:

* `-L`, which indicates we are doing local port forwarding.
* `-f` puts the ssh process in the backgroundand so you can close your terminal
and keep the tunnel alive
* `-N` tells ssh not to execute a remote command.

If you have successfully set up this tunnel, you can now go to your browser and type
'localhost:3333' and see the web service running in your local machine, which is actually
hosted on a remote machine on a different port, magic!

This same trick can be accomplished on windows,
follow [these instructions](http://howto.ccs.neu.edu/howto/windows/ssh-port-tunneling-with-putty/)
