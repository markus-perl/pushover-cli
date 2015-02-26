pushover
==========

pushover is a simple client for https://pushover.net/ to send pushover notifications through the command line.
Moreover it is possible with this client to pipe streams to your cellphone like tail -f /var/log/my.log | pushover -c

Requirements
------------
* Linux or Mac OSX
* Python 2.7


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


Contact
-------
* Github: [http://www.github.com/markus-perl/pushover](http://www.github.com/markus-perl/pushover)
