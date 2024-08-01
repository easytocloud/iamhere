![release workflow](https://github.com/easytocloud/iamhere/actions/workflows/release.yml/badge.svg)

# iamhere

Change security group to allow traffic from your current IP address.

# sample usage 

Create a security group in your AWS account.
Create a security group rule in it that allows for http traffic from 
address 127.0.0.1 and put the string *myHomeIP* (for example) in the description.

Note: That is the literal string, not your home IP address.

To change this security group to allow traffic not from 127.0.0.1, but from your current IP address, run

```
iamhere myHomeIP
```

Where ``iamhere`` is the name of the script in this repository and the string *myHomeIP* is used to match the SG rule(s).

NOTE: *myHomeIP* is just an example, you should put a more usefull description!

You can have several matching SecurityGroup Rules, in either a single on or multiple SecurityGroups.

This tool is particulary usefull when your IP address changes between many different IP addresses
and you want to limit access using a SG with just that IP address.

# options

iamhere supports two options:

 - -v for verbose, by default it does its work in silence
 - -c to remove your IP address from the rule and change it to 127.0.0.1 (essentially blocking external traffic)

# environment variables

If your environment has a variable ``${DEFAULT_IAMHERE_TAG}`` this value is used when no arguments are passed.
It defaults to myHomeIP.

The tool also uses your ``${AWS_PROFILE}`` to contact an AWS account in the AWS region that the profile refers to.
In addition, it supports ``${AWS_DEFAULT_REGION}`` should you need to make modifications in other regions than used by the profile.

# installation

Use homebrew or just copy iamhere from this repository to any directory in your ``${PATH}``

```
brew install easytocloud/tap/iamhere
```
or just
```
brew install iamhere
```
if you already use our tap.
