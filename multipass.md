### List view (if prior ubuntu instance ever exist): 
	multipass list
### For info:
	multipass info
### Network check:
	multipass networks
### (remember the network name in output -> `<network-name>` )
	
### Want to delete existing and create a new one: 
1) First, stop the instance (just to be safe):
	```bash 
	multipass stop <instance-name>
2) Then delete it:
	```bash
	multipass delete <instance-name>	
3) And purge it from the system:
	```bash
	multipass purge
### Now, create a fresh Ubuntu instance. 
### Choose a version or go with the default (latest LTS):
	multipass launch --network <network-name> --name <instance-name>
### Or specify a version:
	multipass launch 22.04 --network <network-name> --name <instance-name>
### Check new instance: 
	multipass list
### Access the New Instance.
	multipass shell <instance-name>	

### Once in multipass now type follwoing in shell:
	sudo vim /etc/ssh/sshd_config
### Now go to the following line and make it `no` to `yes` 
	KbdInteractiveAuthentication no
### After changing
	KbdInteractiveAuthentication yes
### Now press `esc` then type `:wq` to exit vim
### Run the following commands:
	sudo systemctl daemon-reload
	sudo service ssh restart
### Now change ubuntu password:
	sudo passwd ubuntu
### Add something fancy, `p` for the new changed password might have to type again for conformation
