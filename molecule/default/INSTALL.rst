*******
Delegated driver installation guide
*******

Requirements
============

Download FortGate KVM image from the following link
(registration required):
https://support.fortinet.com/Download/VMImages.aspx

And extract the orginal image to a path then
configure it in molecule.yml

::

  platforms:
    - name: fortios
      image_file: /home/onagano/tmp/fortios.qcow2
      admin_password: RedHat1!

Make sure that "ansible_python_interpreter" indicates
a proper virtualenv which has "fortiosapi" installed.

::

  inventory:
    group_vars:
      all:
        ansible_python_interpreter: ${MOLECULE_PROJECT_DIRECTORY}/.tox/py37/bin/python


Run the test
=======


::

  MOLECULE_NO_LOG=false molecule test --destroy never




References
=======

Documentation:
https://docs.fortinet.com/vm/kvm/fortigate/6.2/kvm-cookbook/6.2.0/767662/cloud-init
