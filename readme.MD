Jenkins Setup
Partition the disk
#!/bin/bash
# ===================================================
# Disk expansion
# ===================================================
growpart /dev/nvme0n1 4

lvextend -L +10G /dev/mapper/RootVG-varVol
lvextend -L +10G /dev/mapper/RootVG-rootVol
lvextend -l +100%FREE /dev/mapper/RootVG-homeVol

xfs_growfs /
xfs_growfs /var
xfs_growfs /home

# Wait for network to be ready
sleep 30

# ===================================================
# Jenkins installation
# ===================================================
curl -o /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key

# Install dependencies first
yum install -y fontconfig java-21-openjdk

# Install Jenkins
yum install -y jenkins

# Start and enable Jenkins service
systemctl daemon-reload
systemctl start jenkins
systemctl enable jenkins

# Logging to check if script ran
echo "User Data script completed at $(date)" >> /var/log/user-data.log
# plugins
Stage view
Master Agent Architecture
Create credentials to connect agent
Install Java in agent
Select Non verification strategy
