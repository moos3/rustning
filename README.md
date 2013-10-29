rustning
========

rustning armor for you ssh keys


rustning means Armor in Old Norse and Danish, German. This is a nice wrapper 
for the ssh-add command that 99.9% of people most likely don't even know about.


## Configuration
.rustning/conf is a JSON file that has the following layout

{
  "myserver.example.com":".myserver.example.com.priv",
  "yourserver.com":".yourserver.com.priv"
}


## How to use

rustning grant-access <all | hostname >

all will allow you to load all the keys in your rustning configuration file.

hostname will just load that one hostname

rustning setup will generate you a blank configuration file and directory
