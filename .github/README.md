# ans_role_config_loader

Configure the FreeBSD _loader_ bootloader.

[![Release](https://img.shields.io/github/release/digimokan/ans_role_config_loader.svg?label=release)](https://github.com/digimokan/ans_role_config_loader/releases/latest "Latest Release Notes")
[![License](https://img.shields.io/badge/license-MIT-blue.svg?label=license)](LICENSE.md "Project License")

## Table Of Contents

* [Purpose](#purpose)
* [Supported Operating Systems](#supported-operating-systems)
* [Quick Start](#quick-start)
    * [Use From Playbook](#use-from-playbook)
* [Role Options](#role-options)
* [Contributing](#contributing)

## Purpose

* Configure the [loader](https://docs.freebsd.org/en/books/handbook/boot/#boot-introduction) bootloader.

## Supported Operating Systems

* FreeBSD.

## Quick Start

### Use From Playbook

1. Create `requirements.yml` in ansible project root, and add this content:

   ```yaml
   # requirements.yml
   - src: https://github.com/digimokan/ans_role_config_loader
   ```

2. From the project root directory, install/download the role:

   ```shell
   $ ansible-galaxy install --role-file requirements.yml --roles-path ./roles --force-with-deps
   ```

   * _NOTE:_ `--force-with-deps` _ensures subsequent calls download updates_

3. Include the role like any local role, from the project playbook:

   ```yaml
   # playbook.yml
   - hosts: localhost
     connection: local
     tasks:
       - name: "Configure the FreeBSD 'loader' bootloader"
         ansible.builtin.include_role:
           name: ans_role_config_loader
         vars:
           load_cpu_microcode_updates: true
   ```

## Role Options

Vars with default values, which can be overridden in the playbook:

  * [overridable](../defaults/main/overridable/main.yml)

## Contributing

* Feel free to report a bug or propose a feature by opening a new
  [Issue](https://github.com/digimokan/ans_role_config_loader/issues).
* Follow the project's [Contributing](CONTRIBUTING.md) guidelines.
* Respect the project's [Code Of Conduct](CODE_OF_CONDUCT.md).

