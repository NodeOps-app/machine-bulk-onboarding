# Atlas Network bulk machine onboarding

This repository contains Ansible for bulk machine onboarding on Atlas Network by Providers. Follow the simple steps below.

## Prereq

- Ansible >=2.17.3

## Setup

- Get the onboarding keys from the <https://testnet.atlasnetwork.xyz/providers>

- Prepare ansible inventory as below when you put those each onbarding key in each machine's `onboarding_key` ansible var with respect to the IP of the machine. make sure you're choosing correct `ansible_user` under `vars` section

  ```inventory
  [all]
  # <public-ip> onboarding_key=<onboarding_key>
  10.0.0.1 onboarding_key=xxxx
  # ...

  [all:vars]
  ansible_user=root
  ```

- Fire in the hole

  ```shell
  ansible-playbook onboard.yaml
  ```
