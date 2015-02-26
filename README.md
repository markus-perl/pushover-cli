pushover-cli
==========

pushover-cli is a command line client for https://pushover.net to send pushover notifications.
Moreover it is possible with this client to pipe streams directly to your cellphone like tail -f /var/log/my.log | pushover-cli -

Requirements
------------
* Linux or Mac OSX
* Python 2.7
* Your own pushover application token, which can be created here: https://pushover.net/apps/build (Type: Script)
* Your pushover user key, which can be found here after logging in: https://pushover.net


Download and installation
-------------------------

Simply execute the following command to install the latest version of this script to your system:

    sudo curl -o /usr/bin/pushover-cli https://raw.githubusercontent.com/markus-perl/pushover-cli/master/pushover-cli && sudo chmod 555 /usr/bin/pushover-cli
    

Commandline options
-------------------

    Usage:   ./pushover-cli [options] <message> <title>
    Stdin:   ./pushover-cli [options] - <title>
    Example: ./pushover-cli -u ubLBe5u3zNXF9gBtX2zKkezSuPgu3v -t aK5BW3sjAqPsedH44VyQSbaQecoRen "Hello World"

      -u --user     <user id>             Pushover User-ID
      -t --token    <api token>           Pushover API-Token
      -p --priority <high, normal, low>   Default: normal
      -l --url      <url>                 Link the message to this URL
      -c --config   <path to file>        Default: /etc/pushover.conf
      -v --verbose                        Be verbose
      -q --quiet                          Be quiet


Config file
-------------------

Every command line option can also be set by creating the config file /etc/pushover-cli.conf

Example file:

    user=ubLBe5u3zNXF9gBtX2zKkezSuPgu3v
    token=aK5BW3sjAqPsedH44VyQSbaQecoRen
    priority=normal
    verbose=0
    quiet=0
    
After creating this file it is no more necessary to specify these options in the command line which makes it more easier to send a message:
    $ pushover "My Message" "My Title"


Contact
-------
* Github: [http://www.github.com/markus-perl/pushover](http://www.github.com/markus-perl/pushover)
