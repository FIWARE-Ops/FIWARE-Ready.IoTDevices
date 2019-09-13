![FIWARE Banner](https://nexus.lab.fiware.org/content/images/fiware-logo1.png)

# FIWARE-Ready IoT Devices (Validator)

## Overview
This project is part of [FIWARE](https://fiware.org) OPS infrastructure.
It has a recipe to redeploy an environment to validate FIWARE-Ready IoT Devices.

## Requirements
  + Server
    + Ubuntu18+
    + `python 2.7` and `setuptools` must be installed, use `sudo apt-get install -y python python-setuptools`
  + Ansible
    + Version 2.3+
    + `config.json` with docker credentials must be put to `docker/`
    + `ansible_host` in `hosts` must be filled in with the external ip of the target host
    + please, verify the value of `MTU` parameter in `docker.yml` and `docker/daemon.json`
  + DNS
    + iot-ready-json.lab.fiware.org should point to a server
    + iot-ready-ul.lab.fiware.org should point to a server

## How to run
When you use this scenario for the first time, execute it with the environment variable `prepare`
```console
$ ansible-playbook -e prepare=True main.yml
```
When this variable is not defined, the scenario executes only `validator.yml`, i.e. it only redeploys validator itself
```console
$ ansible-playbook main.yml
```
