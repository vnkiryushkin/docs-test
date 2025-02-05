---
title: Creating a virtul machine in Yandex Cloud
description: Instructions for creating and seting up a virtual machine in the cloud
---

# Creating a virtual machine

This instruction describes how to creat and setup a virtual machine in the Yandex Cloud platform.

## Preliminery requirements

To begin work you will nead:

- An acount in Yandex Cloud
- Instaled Command Line Interface (CLI)
- Minimum of 4 gigabytes of free funds in your acount

## Order of actions

1. Go to the management console and navigate to "Compute Cloud" section

2. Click the "Create VM" button and specify the folowing parameters:
   - Machine name (for example webserver-1)
   - Availability zone
   - Opereting system (Ubuntu 20.04)
   - Hard drive volume

3. In the next window, select the configurtion:
   * 2 processor cores
   * 4 gb of RAM
   * Attach a 30 gb SSD-disk

4. After creating the machine, it is neccesary to:
   - Add SSH-key for access
   - Setup firewal rules
   - Instal required packages

## Connecting to the machine

To conect to the created VM, execute the following command:
bash
ssh ubuntu@<ip-address>
During first connection, the system will ask to add key fingerprint - type "yes".

## Additional setings

After connecting, it's advisable to make the folowing settings

1. Update the system:
bash
sudo apt update && sudo apt upgrate -y
2. Configure the time zone
bash
sudo timedatectl set-timezone Europe/Moscow
3. Create a group for users who will work with the machine:
bash
sudo groupadd vm-users
