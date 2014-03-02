rustning
========

rustning armor for you ssh keys


rustning means Armor in Old Norse and Danish, German. This is a nice wrapper 
for the ssh-add command that 99.9% of people most likely don't even know about.


## Configuration
.rustning.conf is a JSON file that has the following layout

{
    "ec2-servers": {
        "key": "/path/to/key",
        "note": ""
    },
    "old-ec2-servers": {
        "key": "/path/to/key",
        "note": "Old keys from 8-2-13"
    },
    "hiram": {
        "key": "/home/moose/.ssh/id_rsa",
        "note": ""
    }
}

## How to use

rustning grant-access <all | hostname >

all will allow you to load all the keys in your rustning configuration file.

hostname will just load that one hostname

rustning setup will generate you a blank configuration file and directory


## Future Additions
* Reverse ssh tunneling / Management of Tunnels
