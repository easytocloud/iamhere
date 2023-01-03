# iamhere
tag-based change security group to allow traffic from your current IP address 

# sample usage 

Create a security group in your AWS account.
Create a security group rule in it that allows for http from address 1.2.3.4 and put 'IamHere' (for example) in the description.

To change this security group to allow traffic not from 1.2.3.4, but from your current IP address, run

```
iamhere IamHere
```
Where iamhere is the script in this repository and IamHere is used to match the SG rule(s).

IamHere is just an example, you can put a more usefull description.

Note that you can have several security group rules, in either a single on or multiple security groups.

This tool is particulary usefull when your IP address changes between many different IP addresses.

The tool uses your ``${AWS_PROFILE}`` to contact the right AWS account in the right AWS region.

# installation

Use homebrew or just copy iamhere from this repository to a directory in your ${PATH}

