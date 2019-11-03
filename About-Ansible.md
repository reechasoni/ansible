## About Ansible

Ansible is an IT automation tool. 

It can configure systems, deploy software, and orchestrate more advanced IT tasks such as continuous deployments or zero downtime rolling updates.

Ansible manages machines in an agent-less manner.

Ansible by default manages machines over the SSH protocol.

## Control Node Requirements

Currently Ansible can be run from any machine with Python 2 (version 2.7) or Python 3 (versions 3.5 and higher) installed. 

Windows isn’t supported for the control node.

This includes Red Hat, Debian, CentOS, macOS, any of the BSDs, and so on.

## Managed Node Requirements

On the managed nodes, you need a way to communicate, which is normally ssh. By default this uses sftp. If that’s not available, you can switch to scp in ansible.cfg. 

You also need Python 2 (version 2.6 or later) or Python 3 (version 3.5 or later).

