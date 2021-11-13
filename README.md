# secure-your-vps-Linux
Create Public and Private Key ,  Server login without password , Disable root login ,Enable specific user password login

1.Create New User
  
    sudo useradd username
    
2.Add Sudo Userpermission
    
    Usermod -aG sudo username

3.Create Publickey in login pc
    
    Ssh_keygen

4.send our public to server
    
   ssh-copy-id username@ip
   Now You can login your server without password
   
5.Disable Root login use ssh
    
    sudo nano /etc/ssh/sshd_conf
    
    PermitRootLogin no
    PubkeyAuthentication yes
    
6.Enable specific user password login
   
    PasswordAuthentication no
    Match User username
    PasswordAuthentication yes
    Match all
    
    save and restart sshd.service

    
7.If you can give a name in server ip (only linux)

  your pc
  
  sudo nano /etc/hosts    
  
  server ip  your favourite name
  
  ex -
  
  192.168.1.19    projectA
    
  
 
  
