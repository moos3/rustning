Rustning
========

Rustning is for managing your private ssh keys

Rustning means Armor in Old Norse and Danish, German. This is a nice wrapper 
for the ssh-add command that 99.9% of people most likely don't even know about.

## Requirements
**MUST HAVE PHP 5.3+**

## Configuration
.rustning.conf is a JSON file that has the following layout
```
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
```

## Usage

```
Usage: rustning <command> <args>

Commands

grant-access   - adds the ssh keys to your chain
   - accepts all or single hostname
add-key <hostname> <path-to-key>
   - adds host and key to the rustning configuration files
del-key <hostname>
   - remove key from rustning configuration file
list-keys
   - list all the keys setup for use
add-note <hostname> <note>
   - add/update note to host entry
```

## How to use

```
rustning grant-access ec2-servers
loading key for ec2-servers

rustning grant-access all
loading key for ec2-servers
loading key for old-ec2-servers
    !!!! Failed to load key for old-ec2-servers, the key file is missing
loading key for hiram

rustning add-key forseti /home/moose/.ssh-keys/forseti
Updated Rustning Configuration

rustning del-key old-ec2-servers
Updated Rustning Configuration

rustning add-note forseti "my mac mini at home"
Updated Rustning Configuration

rustning list-keys
host                notes
----                -----
ec2-servers         current ec2 server keys
old-ec2-servers     old ec2 server keys that might still around
hiram               my laptops ssh key
forseti             my mac mini at home

```

## Future Additions
* Reverse ssh tunneling / Management of Tunnels
