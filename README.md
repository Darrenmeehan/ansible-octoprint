# Octoprint

Setup a Linux machine with [Octoprint](https://octoprint.org/)

## TODO

[] Setup HA Proxy
[] Setup TLS
[] Add management of plugins
[] Add backup/restore of settings
[] Test upgrade flow

## Setup

  1. [Install Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html). The easiest way (especially on Pi or a Debian system) is via Pip:
     1. (If on Pi/Debian): `sudo apt-get install -y python3-pip`
     2. (Everywhere): `pip3 install ansible`
  2. Clone this repository: `git clone https://github.com/darrenmeehan/octoprint.git`, then enter the repository directory: `cd octoprint`.
  3. Install requirements: `ansible-galaxy collection install -r requirements.yml` (if you see `ansible-galaxy: command not found`, restart your SSH session or reboot the Pi and try again)
  4. Make copies of the following files and customize them to your liking:
     - `example.inventory.ini` to `inventory.ini` (replace IP address with your Pi's IP, or comment that line and uncomment the `connection=local` line if you're running it on the Pi you're setting up).
     - `example.config.yml` to `config.yml`
  5. Run the playbook: `ansible-playbook main.yml --ask-become-pass`

> **If running locally on the machine**: You may encounter an error like "Error while fetching server API version". If you do, please either reboot or log out and log back in, then run the playbook again.

## License

MIT

## Author

This project was created in 2022 by [Darren Meehan](https://drn.ie).
