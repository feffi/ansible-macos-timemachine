# ansible-macos-timemachine
Ansible role to manage timemachine settings in macOS.

[![Build Status](https://img.shields.io/travis/feffi/ansible-macos-timemachine.svg)](https://travis-ci.org/feffi/ansible-macos-timemachine) [![Github All Releases](https://img.shields.io/github/downloads/feffi/ansible-macos-timemachine/total.svg)](https://github.com/feffi/ansible-macos-timemachine) [![GitHub forks](https://img.shields.io/github/forks/feffi/ansible-macos-timemachine.svg?style=social&label=Fork)](https://github.com/feffi/ansible-macos-timemachine) [![GitHub stars](https://img.shields.io/github/stars/feffi/ansible-macos-timemachine.svg?style=social&label=Star)](https://github.com/feffi/ansible-macos-timemachine) [![GitHub watchers](https://img.shields.io/github/watchers/feffi/ansible-macos-timemachine.svg?style=social&label=Watch)](https://github.com/feffi/ansible-macos-timemachine) [![Twitter Follow](https://img.shields.io/twitter/follow/feffi1.svg?style=social&label=Follow)](https://twitter.com/feffi1) [![License](http://img.shields.io/:license-mit-blue.svg)](https://github.com/feffi/ansible-macos-timemachine/blob/master/LICENSE)

## Requirements
- Ansible 2.3

### ansible.cfg
```
hash_behaviour = merge
```

## Install
Just add the role to your ``requirements.yml`` file:
```yaml
- src: https://github.com/feffi/ansible-macos-timemachine.git
  name: feffi.macos-timemachine
```

## Role Variables
All role based variables are listed below, along with default values:

```yaml
macos_timemachine:
  # Disable local Time Machine snapshots
  local: false

  # Prevent Time Machine from prompting to use new hard drives as backup volume
  prompt_new: false
```

## Dependencies
None.

## Example Playbook

```yaml
    - hosts: all
      vars:
        macos_timemachine:
          local: false
          prompt_new: false
      roles:
        - { role: feffi.macos-timemachine }
```
Or with local parameters:

```yaml
    - hosts: all
      roles:
        - { role: feffi.macos-timemachine,
            macos_timemachine: {
              local: false,
              prompt_new: false
            }
          }
```
