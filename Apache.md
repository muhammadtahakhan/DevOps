# Apache

# Now open ports 22 (for SSH), 80 and 443 and enable Ubuntu Firewall (ufw):
sudo apt update
sudo apt upgrade



# Install Apache using apt:
sudo apt install apache2

# Confirm that Apache is now running with the following command:
sudo systemctl status apache2


# Now open ports 22 (for SSH), 80 and 443 and enable Ubuntu Firewall (ufw):
sudo ufw allow ssh
sudo ufw allow 80
sudo ufw allow 443
sudo ufw enable

# make sure that your firewall allows HTTP and HTTPS traffic.
sudo ufw app list

# If you look at the Apache Full profile details, you’ll see that it enables traffic to ports 80 and 443:
sudo ufw app info "Apache Full"

# To allow incoming HTTP and HTTPS traffic for this server, run:
sudo ufw allow "Apache Full"