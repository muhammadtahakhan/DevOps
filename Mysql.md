# MariaDb/Mysql

# Install the required packages:
sudo apt install mariadb-server mariadb-client


# Once installed, check it’s running correctly:
sudo systemctl status mariadb


# Secure your newly installed MariaDB service:
sudo mysql_secure_installation

As you have no root password set for MariaDB you should simply press Enter when prompted, pressing Y on the next question to then set a root password (keep this safe and secure!) With that set, you can press Enter for the remaining questions as the defaults for each of these will help to secure your new installation.
