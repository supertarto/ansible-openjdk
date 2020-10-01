# Ansible OpenJDK
[![Build Status](https://travis-ci.com/supertarto/ansible-openjdk.svg?branch=master)](https://travis-ci.com/supertarto/ansible-openjdk)

Role to install and configure openjdk with ansible

## Requirements
None

## Tested plateform
* Debian 10 (Buster)

## Role variables
Default variables. They define the path where the JVM will be installed and the path where the symlink to default-java will be. 
```yml
openjdk_jvm_path: "/usr/lib/jvm"
openjdk_default_java_link: "{{ openjdk_jvm_path }}/default-java"
```
OS specific variables. If not explicitly defined elsewhere, those will be used. 
```yml
__openjdk_packages:
  - openjdk-8-jdk
__openjdk_dir_name: "java-8-openjdk-amd64"
__openjdk_java_full_path: "{{ openjdk_jvm_path }}/{{ openjdk_dir }}"
```

## Examples
```yml
---
- hosts: somehost
  roles:
    - supertarto.openjdk
  vars:
    openjdk_packages:
        - openjdk-11-jre
    openjdk_dir_name: "java-11-openjdk-amd64"    
```
## Installation
```
ansible-galaxy install supertarto.openjdk
```
## License
GPL V3.0
