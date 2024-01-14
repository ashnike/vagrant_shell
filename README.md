# Vagrant CentOS Stream 9 Box with Apache and Barista Cafe

This Vagrant configuration sets up a CentOS Stream 9 virtual machine with Apache installed and the Barista Cafe website deployed.

## Prerequisites

Before getting started, ensure you have the following installed on your machine:

- [Vagrant](https://www.vagrantup.com/)
- [VirtualBox](https://www.virtualbox.org/)

## Getting Started

1. **Clone this repository:**

    ```bash
    git clone https://github.com/ashnike/vagrant_shell.git
    cd vagrant_shell
    ```

2. **Start the virtual machine:**

    ```bash
    vagrant up
    ```

3. **Access the virtual machine:**

    ```bash
    vagrant ssh
    ```

## Configuration Details

- The CentOS Stream 9 box is provided by [eurolinux-vagrant/centos-stream-9](https://app.vagrantup.com/eurolinux-vagrant/boxes/centos-stream-9).
- Private IP: `192.168.60.10`
- Public network bridged to `eno1`.
- Apache is installed and configured.
- Barista Cafe website is deployed.

## Customization

Feel free to modify the `Vagrantfile` or provisioning script to suit your specific needs. You can change IP addresses, adjust memory settings, or customize the provisioning script.

## Cleaning Up

To destroy the virtual machine:

```bash
vagrant destroy
