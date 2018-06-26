dotmjs.ipmi_booted
=========

A role to set the boot device via IPMI and start boot process

Requirements
------------

Host that this role will be executed from (localhost by default, but overriden by ipmi_delegate var) must have network access to IPMI interface on target system.

Role Variables
--------------
- ipmi_host: hostname or IP address of IPMI interface
- ipmi_user: username with permission to set boot device and change power status
- ipmi_password: password for ipmi_user
- ipmi_bootdev (if omitted, defaults to 'default'): boot device to be used for next boot (see possible bootdev values here: https://docs.ansible.com/ansible/2.5/modules/ipmi_boot_module.html)
- ipmi_delegate (if omitted, defaults to 'localhost'): host to execute IPMI from, must have access to IPMI interface on remote system.


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: dotmjs.ipmi_booted, ipmi_bootdev: 'network' }

License
-------

BSD
