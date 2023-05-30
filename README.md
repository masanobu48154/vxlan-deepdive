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

Log in to DevBox.

```shell
$ ssh -l developer 10.10.20.50
developer@10.10.20.50's password:
(py3venv) [developer@devbox ~]$
```

Clone the vxlan-deepdive repository.

```shell
(py3venv) [developer@devbox ~]$ git clone https://github.com/masanobu48154/vxlan-deepdive.git
Cloning into 'vxlan-deepdive'...
remote: Enumerating objects: 33, done.
remote: Counting objects: 100% (33/33), done.
remote: Compressing objects: 100% (25/25), done.
remote: Total 33 (delta 9), reused 29 (delta 8), pack-reused 0
Unpacking objects: 100% (33/33), done.
(py3venv) [developer@devbox ~]$ 
```

Go to the iosxr-nc-ned directory and set the CML2 username and password as environment variables.

```shell
(py3venv) [developer@devbox ~]$ cd vxlan-deepdive/
(py3venv) [developer@devbox iosxr-nc-ned]$ export CML_USERNAME={ CML USERNAME }
(py3venv) [developer@devbox iosxr-nc-ned]$ export CML_PASSWORD={ CML PASSWORD }
(py3venv) [developer@devbox iosxr-nc-ned]$ export CML_LAB={ Your cmlyaml file }
```

Store your lab configuration files in the cmlyaml directory.

Run cml2.py.

It will take about sone minutes to boot up, so have a cup of coffee and wait.

```shell
(py3venv) [developer@devbox vxlan-deepdive]$ python3 cml2.py 
Getting Authentication token
11cfbf51-aec0-4baa-843f-5f248f3ec811
Lab deleted !! Lab ID = 11cfbf51-aec0-4baa-843f-5f248f3ec811
Getting Authentication token
Importing lab
Lab imported !! Lab ID = f8b7bbb5-b2f2-43f5-8f2f-eb0e04b8e171
Lab started !! Lab ID = f8b7bbb5-b2f2-43f5-8f2f-eb0e04b8e171
(py3venv) [developer@devbox vxlan-deepdive]$ 
```

Go to https://10.10.20.161 and log in to CML to verify that your lab has been imported.

