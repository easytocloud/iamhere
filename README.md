# iamhere
tag-based change security group to allow traffic from your current IP address. 

# sample usage 

Create a security group in your AWS account.
Create a security group rule in it that allows for http traffic from 
address 1.2.3.4 and put *HomeIP* (for example) in the description.

To change this security group to allow traffic not from 1.2.3.4, but from your current IP address, run

```
iamhere HomeIP
```

Where ``iamhere`` is the name of the script in this repository and *HomeIP* is used to match the SG rule(s).

NOTE: *HomeIP* is just an example, you should put a more usefull description!

You can have several SecurityGroup Rules, in either a single on or multiple SecurityGroups.

This tool is particulary usefull when your IP address changes between many different IP addresses
and you want to limit access using a SG.

# environment

The tool uses your ``${AWS_PROFILE}`` to contact the right AWS account in the right AWS region.

If your environment has a variable DEFAULT_IAMHERE_TAG this value is used when no arguments are passed.
It defaults to myHomeIP.

# installation

Use homebrew or just copy iamhere from this repository to a directory in your ${PATH}

```
homebrew install easytocloud/iamhere
```
