# please refer to project 1 
refer to project 1 to spinning up an ubuntu server associating it with an elastic ip

# Install Nginx and Setup Your Website
Execute the following commands.
sudo apt update

sudo apt upgrade

sudo apt install nginx

Start your Nginx server by running the sudo systemctl start nginx command, enable it to start on boot by executing sudo systemctl enable nginx, and then confirm if it's running with the sudo systemctl status nginx command.

Visit your instances IP address in a web browser to view the default Nginx startup page.

Download your website template from your preferred website by navigating to the website, locating the template you want.

Right click and select Inspect from the drop down menu.
[![alt text](<img 1.png>)]


# click on network tab
[![alt text](<img 2.png>)]

# Then scroll down and click on the download button

# After downloading
still in the network tab click on the the downloaded and go to the the copy,and under the copy click on copy link address
[![alt text](<Screen Shot 2024-08-31 at 14.26.21.png>)]

# To install the unzip tool
just run the command sudo apt install unzip

# To download the websites template unto your server
Execute the command to download and unzip your website files sudo curl -o /var/www/html/2098_health.zip https://www.tooplate.com/zip-templates/2098_health.zip && sudo unzip -d /var/www/html/ /var/www/html/2098_health.zip && sudo rm -f /var/www/html/2098_health.zip.
[![alt text](<Screen Shot 2024-08-31 at 14.34.39.png>)]

# Dowload the contents of your second websites
enter this command to download the 2nd websites template
[sudo curl -o /var/www/html/2132_clean_work.zip https://www.tooplate.com/zip-templates/2132_clean_work.zip && sudo unzip -d /var/www/html/ /var/www/html/2132_clean_work.zip && sudo rm -f /var/www/html/2132_clean_work.zip]

# Notes:
when you download the websites template ,if yours is different from 2132_clean_work.zip and the health zip you have to edit the commands to what you downloaded

# set up the websites configuration
To set up your website's configuration, start by creating a new file in the Nginx sites-available directory. Use the following command to open a blank file in a text editor: sudo nano /etc/nginx/sites-available/cleaning
[![alt text](<Screen Shot 2024-09-02 at 08.52.55.png>)]

 # Copy and paste the following code into the open text editor.
server {
    listen 80;
    server_name example.com www.example.com;

    root /var/www/html/example.com;
    index index.html;

    location / {
        try_files $uri $uri/ =404;
    }
}
# Edit the root directive within your server block to point to the directory where your downloaded website content is stored.
[![alt text](<Screen Shot 2024-09-02 at 08.59.20.png>)]

# Configure your second website by creating a new file:
 in the Nginx sites-available directory with the following command: sudo nano /etc/nginx/sites-available/health.
[![alt text](<Screen Shot 2024-09-02 at 09.09.03.png>)]


 # Edit the root directive within your server block to point to the directory where your downloaded website content is stored.
 [![alt text](<Screen Shot 2024-09-02 at 09.11.48.png>)]

# Configure your second website by creating a new file in the Nginx sites-available directory with the following command: sudo nano /etc/nginx/sites-available/health.
[![alt text](<Screen Shot 2024-09-02 at 09.09.03.png>)] 

# Then do what we did before and edit the root directive 
With what you downloaded 
[![alt text](<Screen Shot 2024-09-02 at 09.11.48.png>)]

# creates a symbolic link for both of the websites by running these commands
1.sudo ln -s /etc/nginx/sites-available/cleaning /etc/nginx/sites-enabled/
2.sudo ln -s /etc/nginx/sites-available/health /etc/nginx/sites-enabled/
[![alt text](<img/Screen Shot 2024-09-06 at 17.07.02.png>)]





