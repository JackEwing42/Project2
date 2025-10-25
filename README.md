# Notes on Project 2

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
- Added `wordle.sh` and `index.html` to UserData
- Created `WSUKDuncan/cheatsheet` container


### Notes to Self

- Add new `Key` and `Value` for each new `Tag`
- Make sure all rules in security group have the same indentation
- Indentation is an important part of Cloud Formation

### Description

A Cloud Formation Template designed to install python3, pip3, apache2, wamerican, and docker. As well as creates the files wordle.sh and the index.html for the wsukduncan/cheatsheet webpage onto the already existing AMI for Project 1. The template is designed to run the VPC on the CIDR of 192.168.0.0/23 and the Subnet CIDR on 192.168.0.0/24 The template also names everything EWING-CF-`ResourceName`. Along with that, the template will also add three rules to the security group that allow for ssh on my home network and allow for all access on ports 8080 and 80. Also added outbound rule for NACL that denies all traffic to wttr.in. The template has been set up with the Private IP of 192.168.0.5.

### Layout

[CF Template Concept Layout.pdf](https://github.com/user-attachments/files/23071327/CF.Template.Concept.Layout.pdf)

### Description of Layout

The layout is set up in a way that highlights each component in the stack. We see that the AWS Cloud contains everything. Inside the cloud is the VPC, set to 192.158.0.0/23 tagged as EWING-CF-VPC. Inside that is the Subnet (EWING-CF-SUBNET) and the Internet Gateway (EWING-CF-IG). Inside that is the EC2 instance showing the base layer of the UserData and the Security Group showing the rules set up. Lastly we have the NACL inside of the EC2 instance showing the given rules. The design is simplistic but shows where each process is contained
