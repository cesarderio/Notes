<img src="../assets/nextcloud.png" alt="Alt Text" width="400">

# Nextcloud Installation Tutorial

Learn how to install and set up Nextcloud, a self-hosted file sync and sharing server, on a Linux server. Maintain full control over your data while storing and sharing files, contacts, calendars, and more.

<br>

### **Table of Contents**

- [Overview](#overview)
- [Objectives](#objectives)
- [Prerequisites](#prerequisites)
- [Steps](#steps)
  - [Install Required Packages](#install-required-packages)
  - [Configure Database](#configure-database)
  - [Download and Install Nextcloud](#download-and-install-nextcloud)
  - [Configure Web Server](#configure-web-server)
    - [Apache Configuration](#apache-configuration)
    - [Nginx Configuration](#nginx-configuration)
  - [Complete Installation via Web Browser](#complete-installation-via-web-browser)
  - [Finalize Configuration](#finalize-configuration)
  - [Secure Your Instance with HTTPS](#secure-your-instance-with-https)
- [Best Practices](#best-practices)
- [Resources](#resources)
- [Contribution](#contribution)

<br>

## **Overview**

Nextcloud is an open-source platform for file storage and synchronization. By hosting your instance, you gain complete control over your data, ensuring privacy and security.

<br>

## **Objectives**

By the end of this guide, you will:

- Install Nextcloud on a Linux server.
- Configure a web server and database.
- Set up HTTPS for secure access.

<br>

## **Prerequisites**

1. **Linux Server**: A server running a Linux distribution (e.g., Ubuntu) with root access.
2. **Domain Name**: Optional but recommended for easier access.
3. **Web Server**: Apache or Nginx installed.
4. **PHP**: Version 7.2 or later installed.
5. **Database Server**: MySQL or MariaDB installed.

<br>

## **Steps**

### **Install Required Packages**

Update your system and install necessary dependencies:

```bash
sudo apt update
sudo apt upgrade
sudo apt install apache2 mariadb-server libapache2-mod-php php-gd php-json php-mysql php-curl php-mbstring php-intl php-imagick php-xml php-zip unzip
```

<br>

### **Configure Database**

Log in to the database server:

```bash
sudo mysql -u root -p
```

Run the following commands to create a database and user:

```sql
CREATE DATABASE nextcloud;
CREATE USER 'nextclouduser'@'localhost' IDENTIFIED BY 'your_password';
GRANT ALL PRIVILEGES ON nextcloud.* TO 'nextclouduser'@'localhost';
FLUSH PRIVILEGES;
EXIT;
```

<br>

### **Download and Install Nextcloud**

Download the latest version of Nextcloud:

```bash
wget https://download.nextcloud.com/server/releases/latest.zip
```

Unzip the downloaded file:

```bash
sudo unzip latest.zip -d /var/www/
```

Set appropriate permissions:

```bash
sudo chown -R www-data:www-data /var/www/nextcloud/
```

<br>

### **Configure Web Server**

#### **Apache Configuration**

Create a virtual host file:

```bash
sudo nano /etc/apache2/sites-available/nextcloud.conf
```

Add the following configuration:

```apache
<VirtualHost *:80>
    ServerAdmin admin@example.com
    DocumentRoot /var/www/nextcloud/
    ServerName your_domain.com

    <Directory /var/www/nextcloud/>
        Options +FollowSymlinks
        AllowOverride All
        Require all granted
    </Directory>

    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

Enable the site and required modules:

```bash
sudo a2ensite nextcloud.conf
sudo a2enmod rewrite headers env dir mime setenvif ssl
sudo systemctl reload apache2
```

#### **Nginx Configuration**

Create a server block file:

```bash
sudo nano /etc/nginx/sites-available/nextcloud
```

Add the configuration:

```nginx
server {
    listen 80;
    server_name your_domain.com;
    root /var/www/nextcloud/;

    index index.php index.html;
    location / {
        try_files $uri $uri/ /index.php;
    }

    location ~ \.php$ {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/var/run/php/php7.4-fpm.sock;
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        include fastcgi_params;
    }

    location ~ /\.ht {
        deny all;
    }
}
```

Enable the site and restart Nginx:

```bash
sudo ln -s /etc/nginx/sites-available/nextcloud /etc/nginx/sites-enabled/
sudo systemctl reload nginx
```

<br>

### **Complete Installation via Web Browser**

Visit `http://your_domain.com` in a browser. Follow the prompts to complete the setup, providing the database credentials created earlier.

<br>

### **Finalize Configuration**

Add your domain to the trusted domains array in the configuration file:

```bash
sudo nano /var/www/nextcloud/config/config.php
```

Example:

```php
'trusted_domains' =>
  array (
    0 => 'localhost',
    1 => 'your_domain.com',
  ),
```

<br>

### **Secure Your Instance with HTTPS**

Install Certbot:

```bash
sudo apt install certbot python3-certbot-apache
```

Obtain and configure a Let's Encrypt certificate:

```bash
sudo certbot --apache -d your_domain.com
```

<br>

## **Best Practices**

- Regularly update Nextcloud and server packages.
- Use strong, unique passwords for your accounts.
- Set up automated backups of your data and configuration.

<br>

## **Resources**

- [Nextcloud Documentation](https://docs.nextcloud.com/): Official guide for advanced configurations.
- [Certbot](https://certbot.eff.org/): Automates SSL certificate installation.
- [DigitalOcean Tutorials](https://www.digitalocean.com/community/tutorials): Additional Linux server management guides.

<br>

## **Contribution**

Your contributions are highly encouraged to enhance this guide:

- Fork the repository.
- Create a new branch:

    ```bash
    git checkout -b my-awesome-feature
    ```

- Make your valuable changes.
- Commit your changes:

    ```bash
    git commit -am 'Added some amazing features'
    ```

- Push to the branch:

    ```bash
    git push origin my-awesome-feature
    ```

- Create a new Pull Request targeting the `Notes` directory.

Contributions are welcome! Feel free to open issues, suggest enhancements, or submit pull requests to improve this guide.

<br>

## **Author**

- **Raphael Chookagian** | [GitHub Profile](https://github.com/cesar-group)

## **Date of Latest Revision**

- 12/10/2024

## **License**

- This guide is provided as-is without any warranties. Users are advised to review and understand the guide before executing any commands.

- This project is licensed under the MIT License. See the LICENSE file for details.
