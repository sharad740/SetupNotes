# Install Frappe ErpNext 
```
echo "Adding PPA Repo" && sudo add-apt-repository ppa:deadsnakes/ppa

echo "Updating System Repo List" && sudo apt-get update -y 

echo "Installing Kernal Headers" && sudo apt install linux-headers-$(uname -r) -y

echo "Installing Python and Dev required packages" && sudo apt-get install python3 python-is-python3 python3-dev python3-setuptools python3-pip virtualenv python3.8 python3.8-venv python3.10 python3.10-venv python3.8-dev python3.8-distutils python3.10-dev software-properties-common build-essential gcc make php8.1-fpm redis-server curl npm nodejs  xvfb libfontconfig wkhtmltopdf supervisor* git -y 



sudo npm install -g yarn

sudo apt autoremove -y

sudo apt-get install mariadb-server -y



sudo service mysql restart

sudo mysql_secure_installation

sudo apt install phpmyadmin -y



echo "Configuring Mysql Character set."

tee -a /etc/mysql/my.cnf << EOF

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





nvm install 14

nvm install 16

nvm install 18

nvm use 14

node -v

pip3 install frappe-bench &> /dev/null

sudo update-locale LANG=en_US.UTF-8 LANGUAGE=en.UTF-8

timedatectl set-timezone "Asia/Katmandu"

sudo systemctl  enable mysql

sudo systemctl  enable redis-server

sudo systemctl  enable php8.1-fpm


```
# Version 13
```
cd ~/

bench init frappe-13 --frappe-branch version-13 --python /usr/bin/python3.8

cd ~/frappe-13



bench get-app https://github.com/frappe/erpnext --branch version-13 && \

bench new-site sajha.erp --db-name='ERP Branch 13' --install-app erpnext --set-default --db-root-password testing321 --force --admin-password testing321 --verbose

```

# Version 14
```

cd ~/

bench init frappe-14 --frappe-branch version-14 --python /usr/bin/python3.10

cd ~/frappe-14



bench get-app https://github.com/frappe/erpnext --branch version-14 && \

bench new-site sajha.erp --db-name='ERP Branch 14' --install-app erpnext --set-default --db-root-password testing321 --force --admin-password testing321 --verbose


```

# Version 15

```
cd ~/

nvm use 18

bench init frappe-15 --frappe-branch version-15 --python /usr/bin/python3.10

cd ~/frappe-15



bench get-app https://github.com/frappe/erpnext --branch version-15 && \

bench new-site sajha.erp --db-name='ERP Branch 15' --install-app erpnext --set-default --db-root-password testing321 --force --admin-password testing321 --verbose



```

# Set bench config maintenance_mode to false 

```
bench set-config maintenance_mode false
```


# Setup supervisor in frappe
```
bench setup supervisor

bench update --no-backup --reset

```
