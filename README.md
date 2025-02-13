# NodeOps Network bulk machine onboarding

This repository contains Ansible for bulk machine onboarding on NodeOps Network by Providers. Follow the simple steps below.

## Prereq

- Ansible >=2.17.3

## Setup

- Get the onboarding keys from the <https://testnet-providers.nodeops.network>

- Prepare ansible inventory as below when you put those each onbarding key in each machine's `onboarding_secret` ansible var with respect to the IP of the machine. make sure you're choosing correct `ansible_user` under `vars` section

  ```inventory
  [all]
  # <public-ip> onboarding_secret=<onboarding_secret>
  10.0.0.1 onboarding_secret=xxxx
  # ...

  [all:vars]
  ansible_user=root
  ```

  Checkout [inventory-example](./inventory-example)

- Fire in the hole

  ```shell
  ansible-playbook onboard.yaml
  ```
