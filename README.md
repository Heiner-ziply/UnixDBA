# UnixDBA
Tools for DBAs working with Unix or Linux accounts on multiple hosts.

## Overview
The DBA working in a large enterprise often faces the challenge of managing accounts on multiple host machines. Private-public key pairs reduce the need for entering passwords. Aliases for common commands can speed up workflow. When provisioned with a new account, automatic detection of database client binaries and modification of the user's PATH is helpful. 

Programs like **expect** and **ansible** make it possible to quickly and consistently set up these conveniences on multiple hosts. This repository contains scripts for that purpose.

## Assumptions
These scripts assume that the user has multiple Unix or Linux accounts on the same network, and is working from one of these accounts on a host (your "control" host) with **/usr/bin/expect** available and using **/bin/bash** as the shell. The user is presumed to be connecting via PuTTY (or KiTTY).

## Instructions
Set up and save a private-public key pair with no passphrase using puttygen (for instructions click [here](https://docs.oracle.com/en/cloud/paas/event-hub-cloud/admin-guide/generate-ssh-key-pair-using-puttygen.html)). In your default PuTTY settings, set the "Private key file for authentication" under "Connection -> SSH -> Auth" to the private key you created. Log on to your control host and create a ".ssh" directory in your home if there is none, then create an authorized_keys file. Both of these must not be writeable by others:

`mkdir -p ~/.ssh`

`touch ~/.ssh/authorized keys`

`chmod 700 ~/.ssh`

`chmod 600 ~/.ssh/authorized keys`
