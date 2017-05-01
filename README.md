# Generic Ansible Playbook to Prepare CentOS Boxes for CoreMedia

`coremedia-centos-development`

This playbook is intended for preparation of CI nodes are other hosts, which need 
to be able to build [CoreMedia][coremedia] workspaces for CoreMedia CMS 9 or 
LiveContext 3 without any other installation steps necessary.


## Setup of the Environment

We rely on the roles `coremedia` for all coremedia hosts and `cmdev` for development 
hosts.

The role `coremedia` provides the (not supported but happily working) OpenJDK for 
users which do not want to include Oracle Java from the default CoreMedia chef 
node configuration.

The role `cmsdev` provides the needed development tools to build a workspace.


## Preparation

Configure relevant hosts in `inventory.properties` or your global ansible hosts 
file (if you haven't done so).

## Usage

Run with: 

```
ansible-playbook -i inventory.properties setup.yml
```


## Collection

This playbook provides:

* Java 8 

for hosts in role `coremedia`, and

* PhantomJS
* Maven
* [SenchaCMD][sencha]

for hosts in role `cmdev` .


## Feedback

Please use the [issues][issues] section of this repository for feedback. 

[sencha]: https://www.sencha.com/products/extjs/cmd-download/
[coremedia]: http://www.coremedia.com/
[issues]: https://github.com/provocon/coremedia-centos-development/issues
