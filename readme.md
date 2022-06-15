
Commands to run:
cd ansible-control
vagrant up
vagrant ssh
cd ~/ansible
ansible-playbook playbook.yml -i hosts.ini



To get the ansible variables gathered from the host we can use the following command:
ansible docker2 -m setup -a 'filter=ansible_distribution_release'

Explanation
https://stackoverflow.com/questions/59145530/why-does-ansible-ad-hoc-debug-module-not-print-variable
The ansible_distribution fact is created implicitly by the setup module when you run a play. You may have noticed this when running a playbook:

TASK [Gathering Facts] ***************************************************************

This is Ansible running the setup module to get information about a remote host. When you're running ad-hoc commands, there is no "gathering facts" step, so these variables aren't available.