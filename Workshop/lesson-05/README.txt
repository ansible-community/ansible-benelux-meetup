# lesson-05 Ad-hoc commands



# TODO 1. Type this to add our secure base box to your VirtualBox, it is re-usable:

     vagrant box add --force dockpack/centos6 dockpack_centos6.box
      
# TODO 2. cd to the 'project' directory using the command shell/Terminal
# TYPE:   vagrant up


# TODO 3. Use an 'Ad-hoc command' to verify if your web server is up. 
If you enter this command in the command shell that is connected to the host name 'control', then you should see the output below:

    ansible web -m ping
 
--------------------------------------------------------------------------------
[vagrant@control project]$ ansible web -m ping
web | success >> {
    "changed": false, 
    "ping": "pong"
}
--------------------------------------------------------------------------------

# TALK: Verify if your group is logged on to the vm 'control'. All systems up?
# HELP? Ask for help if needed.

The command 'ansible' works on a subset of your inventory ('all' in the above case), and each 'ansible' invocation can use one 'module' (that is what '-m' stands for). 

A 'module' can optionally accept 'arguments' (that is what the '-a' stands for). If you don't specify a module, then 'command' is the default.

# TODO 4. Check what other modules you can use.

    ansible-doc -l

# TODO 5. Verify the free memory on all hosts

    ansible all -m shell -a free

# TODO 6. Verify the disk space on /var of the web server.

    ansible web -a 'df -h /var'

