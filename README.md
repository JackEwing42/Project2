# Notes on Project 2

### Description

### Setup
- Downloaded and added base CF Template to current repo
- Edited description to include purpose of Template
- Edited SSH Location to current IP Address
- Edited AMI to be that of Project 1
- Edited VPC CIDR to 192.168.0.0/23
- Edited Subnet CIDR to 192.168.0.0/24
- Edited Security Group<br>
&ensp; - Added rule for SSH on Port 22 for 192.168.0.0/24<br>
&ensp; - Added rule for HTTP on Port 80 for all IP Sources<br>
&ensp; - Added rule for HTTP on Port 8080 for all IP Sources<br>
- Tagged all resources as `EWING-CF-Resource`
- Edited Values to `Project2 Resource`
- Added Outbound rule to NACL<br>
&ensp; - Deny all outgoing traffic to `wttr.in`<br>
- Edited PrivateIPAddress to `192.168.0.5`
- Edited UserData<br>
&ensp; - Added `hostnamectl set-hostname EWING-AMI && \`<br>
&ensp; - Added `python3 \`<br>
&ensp; - Added `python3-pip \`<br>
&ensp; - Added `apache2 \`<br>
&ensp; - Added `wamerican \`<br>
&ensp; - Added `docker.io \`<br>


### Notes to Self

- Add new `Key` and `Value` for each new `Tag`
- Make sure all rules in security group have the same indentation



### Layout

[CF Template Concept Layout.pdf](https://github.com/user-attachments/files/23071327/CF.Template.Concept.Layout.pdf)
