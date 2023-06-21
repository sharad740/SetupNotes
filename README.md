# Frappe-tutorials
Guide to frappe

### Git and Python setup
```
sudo apt update
sudo apt-get install git -y
sudo apt-get install python3 python3-dev -y
sudo apt-get install python3-setuptools python3-pip -y
sudo apt-get install virtualenv -y
```

    3  sudo apt-get install git
    4  sudo apt-get install python3-dev
    5  sudo apt-get install python3-setuptools python3-pip
    6  sudo apt-get install virtualenv
    7  sudo apt install python3.8-venv
    8  apt install software-properties-common
    9  sudo apt install software-properties-common
   10  sudo add-apt-repository ppa:deadsnakes/ppa
   11  sudo apt install python3.8
   12  sudo apt install python3.8-venv  -y
   13  python3 -V
   14  sudo apt-get install software-properties-common
   15  sudo apt install mariadb-server
   16  sudo mysql_secure_installation
   17  sudo apt-get install libmysqlclient-dev
   18  sudo nano /etc/mysql/mariadb.conf.d/50-server.cnf
   19  sudo service mysql restart
   20  sudo apt-get install redis-server
   21  sudo apt install curl
   22  curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash
   23  source ~/.profile
   24  bash
   
sudo apt install python3.8-venv


nvm install 14.15.0

sudo apt-get install npm
sudo npm install -g yarn
sudo apt-get install xvfb libfontconfig wkhtmltopdf
sudo -H pip3 install frappe-bench
bench --version
bench init frappe-bench --frappe-bench version-13 --python /usr/bin/python3.8
bench init frappe-bench
sudo apt-get -y install supervisor
sudo nano /etc/supervisor/supervisord.conf

```
sudo -A systemctl restart supervisor
supervisor restart frappe
sudo systemctl enable supervisor
```
