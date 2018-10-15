# openshift-aws-setup

## Overview

This is an Ansible auotmation playbook that provisions a small OpenShift environment (1 master, x app nodes) that is suitable for demos, POCs and small workshops. The playbook can deploy either Origin or Container Platform.

AWS related configuration can be customised by modifying ```vars/aws-config.yaml```. Note that the number of application nodes is configurable, the default is 3.

## Usage

Please see the branch that matches the version of OpenShift you want to install for usage instructions and further details.

## Network Topology

![Network Diagram](./docs/network-topology-openshift.jpg)

A private VPC and DNS is used, OpenShift is installed using the private IP addresses. This means the IP addresses never change, unlike EC2 public addresses, and the environment can be stopped and started as needed.
install_node_selector
A bastion is created as part of the installation, however once the installation is complete it is no longer needed and may be stopped or terminated. Note that it can be handy to keep the bastion around in a stopped state in case you want to manually re-run the installation again.

## References

 - https://www.codeproject.com/Articles/1168687/Get-up-and-running-with-OpenShift-on-AWS
 - https://docs.openshift.org/latest/welcome/index.html