SQL Injection on DVWA (Low Security)
Install DVWA (Ubuntu/Kali)
sudo apt install apache2 mariadb-server php php-mysqli git -y
cd /var/www/html
sudo git clone https://github.com/digininja/DVWA.git

Configure DVWA
cd DVWA/config
sudo cp config.inc.php.dist config.inc.php


Edit database credentials:

sudo nano config.inc.php

Start services
sudo systemctl start apache2
sudo systemctl start mysql

Access DVWA

Browser:

http://localhost/DVWA


Click Create DB

Login:

admin / password


Set security → Low

SQL Injection test

Go to:

SQL Injection page


Input:

' OR '1'='1


Screenshot result.

Save exploit script
nano sql_injection_exploit.sh


Example:

#!/bin/bash
echo "Use payload: ' OR '1'='1"
