# IS 565 February Creation

## Team Members
- Brock May
- David Holdstock
- Josh Snyder
- Joseph Curtis
- Tucker Weibell

## Overview
This project allows for people to install basic tools we learned in class on a new ubuntu vm

NOTE: Ansible is **NOT** supported on Windows natively

It is though supported on macOS and most Linux distros

## Setup

### Installing Ubuntu
- Download an Ubuntu ISO from [here](https://ubuntu.com/download)
- Install Ubuntu in a VM

### Getting IP Address of VM
- In the VM's terminal, type `sudo apt install net-tools`
- Then type `ipconfig`

### Hosts
- Clone this repo and go to the root directory of the project
- Open `inventory/hosts`
- Replace `PUT IP ADDRESS OF VM HERE` with the IP of your VM

### sshpass
It is likely that you will need to install `sshpass` on your host system, a package that allows for ansible to use ssh via passwords.

- On a Mac:
    - `brew tap esolitos/ipa`
    - `brew install esolitos/ipa/sshpass`
- On Ubuntu:
    - `sudo apt install sshpass`

## Installing Ansible

You can follow the instructions [here](https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html) to install Ansible.

For macOS, it is as simple as entering `brew install ansible`

## Running the script
Now that you are setup, you can go ahead and run the ansible playbook going to the project's root directory and typing the following into the terminal:

`ansible-playbook ./playbooks/install.yml --user <YOUR_UBUNTU_VM_USERNAME_HERE> --ask-pass --ask-become-pass -i ./inventory/hosts`

It will prompt for you to enter a SSH password and a BECOME root password. This will be the same as your vm user's password.

Once this is done, it will run the playbook

