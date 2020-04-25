pushover-cli
==========

pushover-cli is a command line client for https://pushover.net to send pushover notifications.
Moreover it is possible with this client to pipe streams directly to your cellphone like tail -f /var/log/my.log | pushover-cli -

Note
----

This is forked from [Markus Perl](https://github.com/markus-perl/pushover-cli)'s work, and is extended by:

1. Python 3.x support
1. Adding support for the `device` parameter (allow you to target specific devices on your account)
1. Incorporating the 2 outstanding PRs on the original code that were open at the time I forked this.  Specifically:
   a. Adding proxy support via the `HTTP_ENV` environment variable
   a. Fixing the `--quiet` flag

Requirements
------------
* Linux (including WSL) or Mac OSX
* Python 3.x
* Your own pushover application token, which can be created here: https://pushover.net/apps/build (Type: Script)
* Your pushover user key, which can be found here after logging in: https://pushover.net


Download and installation
-------------------------

Simply execute the following command to install the latest version of this script to your system:

    sudo curl -o /usr/bin/pushover-cli https://raw.githubusercontent.com/scottjwalter/pushover-cli/master/pushover-cli && sudo chmod 555 /usr/bin/pushover-cli
    

Commandline options
-------------------

```
Usage:   pushover-cli [options] <message> <title>
Stdin:   pushover-cli [options] - <title>
Example: pushover-cli -u ubLBe5u3zNXF9gBtX2zKkezSuPgu3v -t aK5BW3sjAqPsedH44VyQSbaQecoRen "Hello World"

    -u --user     <user id>             Pushover User-ID
    -t --token    <api token>           Pushover API-Token
    -d --device   <device name>         Device Name (if omitted, will broadcast to all devices)
    -p --priority <high, normal, low>   Default: normal
    -l --url      <url>                 Link the message to this URL
    -c --config   <path to file>        Default: /etc/pushover.conf
    -v --verbose                        Be verbose
    -q --quiet                          Be quiet
```

Proxy Utilization
-------------------

Incorporating the PR from acaranta that enabled proxy support, if the `HTTP_ENV` environment variable is 
pointed at a proxy server URL, `pushover-cli` will treat that as the proxy gateway and route the message
to Pushover through it.


Config file
-------------------

Every command line option can also be set by creating the config file /etc/pushover-cli.conf

Example file:

```
user=<Pushover User ID>
token=<Pushover Application API Token>
priority=normal
verbose=0
quiet=0
```

After creating this file it is no more necessary to specify these options in the command line which makes it more easier to send a message:
```sh
$ pushover "My Message" "My Title"
```

or

```sh
$ pushover -d 'my_phone' 'My Message' 'My Title'
```
