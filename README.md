# Howtos

## Accessing another computer with ssh

Given that I want to access an account, lets say <em>rafael</em>,
on a computer with IP address known, then
```
ssh rafael@IPADDRESS
```
will make the ssh connection.

On the server side, the service must be started
```
systemctl status sshd
systemctl start  sshd
systemctl enable sshd
```
it might be also necessary to configure the firewall.
In my case, the firewall is the <em>firewalld</em>.
First check if ssh is enabled
```
firewall-cmd --get-services |grep -o "ssh"
```
If <em>ssh</em> appears then everything is fine. In case contrary
do
```
firewall-cmd --add-service ssh --permanent
```

## Changing a string value on BASH
