pushover
==========

pushover is a simple client for https://pushover.net/ to send pushover notifications through the command line.
Moreover it is possible with this client to pipe streams to your cellphone like tail -f /var/log/my.log | pushover -

Requirements
------------
* Linux or Mac OSX
* Python 2.7


Download and installation
-------------------------

Simply execute the following command to install the latest version of this script to your system:

    sudo curl -o /usr/bin/pushover https://raw.githubusercontent.com/markus-perl/pushover/master/pushover && sudo chmod 555 /usr/bin/pushover
    

Commandline options
-------------------

    Usage:   ./pushover [options] <message> <title>
    Stdin:   ./pushover [options] - <title>
    Example: ./pushover -u ubLBe5u3zNXF9gBtX2zKkezSuPgu3v -t aK5BW3sjAqPsedH44VyQSbaQecoRen "Hello World"

      -u --user     <user id>             Pushover User-ID
      -t --token    <api token>           Pushover API-Token
      -p --priority <high, normal, low>   Default: normal
      -l --url      <url>                 Link the message to this URL
      -c --config   <path to file>        Default: /etc/pushover.conf
      -v --verbose                        Be verbose
      -q --quiet                          Be quiet


Config file
-------------------

Every command line option can be set by creating the config file /etc/pushover.conf

Example file:

    user=ubLBe5u3zNXF9gBtX2zKkezSuPgu3v
    token=aK5BW3sjAqPsedH44VyQSbaQecoRen
    priority=normal
    verbose=0
    quiet=0
    
After creating this file it is no more necessary to specify this options in the command line so a message could easily be sent by
    $ pushover "My Message" "My Title"


Contact
-------
* Github: [http://www.github.com/markus-perl/pushover](http://www.github.com/markus-perl/pushover)
