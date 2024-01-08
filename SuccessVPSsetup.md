# OS Info

```
PRETTY_NAME="Ubuntu 22.04.3 LTS"
NAME="Ubuntu"
VERSION_ID="22.04"
VERSION="22.04.3 LTS (Jammy Jellyfish)"
VERSION_CODENAME=jammy
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=jammy
```

# Setup Server
```
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt-get update -y
sudo apt install linux-headers-$(uname -r) -y
sudo apt-get install pkg-config php libapache2-mod-php python3 python-is-python3 python3-dev python3-setuptools python3-pip virtualenv python3.8 python3.8-venv python3.10 python3.10-venv python3.8-dev python3.8-distutils python3.10-dev software-properties-common build-essential gcc make php8.1-fpm redis-server curl npm nodejs  xvfb libfontconfig wkhtmltopdf supervisor* git -y
sudo apt install docker docker-compose docker.io -y
sudo npm install -g yarn
sudo apt autoremove -y
sudo apt-get install mariadb-server -y
sudo service mysql restart
sudo mysql_secure_installation
sudo apt install phpmyadmin -y
sudo tee -a /etc/mysql/my.cnf << EOF
[mysqld]
character-set-client-handshake = FALSE
character-set-server = utf8mb4
collation-server = utf8mb4_unicode_ci

[mysql]
default-character-set = utf8mb4
EOF
sudo service mysql restart
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash
source ~/.profile
nvm install 18
node -v
timedatectl set-timezone "Asia/Katmandu"
sudo systemctl  enable mysql
sudo systemctl  enable redis-server
sudo systemctl  enable php8.1-fpm
sudo systemctl  enable apache2
```

Apache site-available/successbusiness.com.conf file:
```
<VirtualHost *:80>
    # ServerName yourdomain.com  # Replace with your actual domain name
    WSGIDaemonProcess success_business python-home=/var/www/successbusiness.com/.venv python-path=/var/www/successbusiness.com/.venv/bin/python3
    WSGIProcessGroup success_business
    WSGIScriptAlias / /var/www/successbusiness.com/success_business/passenger_wsgi.py
    DocumentRoot /var/www/successbusiness.com/public_html
    
    <Directory /var/www/successbusiness.com/success_business>
        <Files passenger_wsgi.py>
            Require all granted
        </Files>
    </Directory>

    Alias /media /var/www/successbusiness.com/public_html/media/
    Alias /assets /var/www/successbusiness.com/public_html/assets/
    
    <Directory /var/www/successbusiness.com/public_html/assets>
        Require all granted
    </Directory>

    <Directory /var/www/successbusiness.com/public_html/media>
        Require all granted
    </Directory>   

    ErrorLog ${APACHE_LOG_DIR}/success_error.log
    CustomLog ${APACHE_LOG_DIR}/success_access.log combined

</VirtualHost>

```
