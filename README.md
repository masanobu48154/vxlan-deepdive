# Devnet Sandbox CML Automation

## Overview

You can launch your lab with Devnet Sandbox CML.

## Requirements

An account that has permission to access the Cisco DevNet sandbox.

## Sandbox used in this demo

Cisco Modeling Labs

## What you do is

+ [Step 1: Connect to the sandbox](#connect-to-the-sandbox-step-1)
+ [Step 2: Change lab network in CML2](#change-lab-network-in-cml2-step-2)

## Step 1: Connect to the sandbox<a name="connect-to-the-sandbox-step-1"></a>

Connect to Cisco Modeling Labs referring to [here](https://developer.cisco.com/docs/sandbox/ "Devnet Sandbox Document").

## Step 2: Change lab network in CML2<a name="change-lab-network-in-cml2-step-2"></a>

You can build your lab by running cml2.py from DevBox.

Store your lab configuration files in the cmlyaml directory.

Log in to DevBox.

```shell
$ ssh -l developer 10.10.20.50
developer@10.10.20.50's password:
Last login: Tue Jul 14 05:34:45 2020
(py3venv) [developer@devbox ~]$
```

Clone the vxlan-deepdive repository.

```shell
(py3venv) [developer@devbox ~]$ git clone https://github.com/masanobu48154/vxlan-deepdive.git
Cloning into 'vxlan-deepdive'...
remote: Enumerating objects: 18, done.
remote: Counting objects: 100% (18/18), done.
remote: Compressing objects: 100% (14/14), done.
remote: Total 18 (delta 2), reused 11 (delta 1), pack-reused 0
Unpacking objects: 100% (18/18), done.
(py3venv) [developer@devbox ~]$ 
```

Go to the iosxr-nc-ned directory and set the CML2 username and password as environment variables.

```shell
(py3venv) [developer@devbox ~]$ cd vxlan-deepdive/
(py3venv) [developer@devbox iosxr-nc-ned]$ export CML_USERNAME={ CML USERNAME }
(py3venv) [developer@devbox iosxr-nc-ned]$ export CML_PASSWORD={ CML PASSWORD }
(py3venv) [developer@devbox iosxr-nc-ned]$ export CML_LAB={ Your cmlyaml file }
```

Run cml2.py.

It will take about sone minutes to boot up, so have a cup of coffee and wait.

```shell
(py3venv) [developer@devbox iosxr-nc-ned]$ python3 cml2.py
Getting Authentication token

(snip)

(py3venv) [developer@devbox iosxr-nc-ned]$
```

Go to https://10.10.20.161 and log in to CML to verify that your lab has been imported.

