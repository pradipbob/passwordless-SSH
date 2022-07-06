# Create passwordless-SSH

passwordless-ssh-setup-on-ec2-instance
Steps for set Passwordless ssh login

create 2 instances one is master and another is slave
login to slave with sudo user and set password to ec2-user using 'passwd ec2-user' command.
open sshd_config file using below command vim /etc/ssh/sshd_config press i for insert in file. change PasswordAuthentication to yes. It's by default no. save file using Esc key and then type :wq
restart service using below cmd service sshd restart
login to master server using sudo user
enter ssh-keygen command and prss enter enter for save public and private key on by default path.
copy key to slave server using below command ssh-copy-id ec2-user@private ip of slave machine
