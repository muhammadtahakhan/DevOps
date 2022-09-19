# Apache

# Now open ports 22 (for SSH), 80 and 443 and enable Ubuntu Firewall (ufw):
sudo apt update
sudo apt upgrade

# Now open ports 22 (for SSH), 80 and 443 and enable Ubuntu Firewall (ufw):
sudo ufw allow ssh
sudo ufw allow 80
sudo ufw allow 443
sudo ufw enable

# Install Apache using apt:
sudo apt install apache2

# Confirm that Apache is now running with the following command:
sudo systemctl status apache2
