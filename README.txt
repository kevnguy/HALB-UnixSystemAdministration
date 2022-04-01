The following is a short descriptions of the files:
demo.sh 		- Shell script used for testing. curl the VIP 10.0.2.100
haproxy.cfg.j2  	- HAproxy configuration template. Ansible will populate the backend with the webservers
haproxy.xml		- HAproxy firewall XML used to add firewall rule
keepalived-backup.conf 	- Configuration file for backup LB
keepalived-master.conf 	- Configuration file for master LB
lb-playbook.yml		- Ansible playbook for automation
server-inv.txt		- Server inventory for Ansible automation (must be filled with correct IPs)

To run Ansible playbook:
Ensure files are in the same directory as playbook
Ensure server-inv.txt is filled with correct IPs of servers
[Ansible will ask for account/ssh password]
Ensure servers are reachable with command: ansible targets -i server-inv.txt -m ping --ask-pass
Configure servers with command: ansible-playbook -b -i server-inv.txt lb-playbook.yml --ask-pass
