## Documentations

# Go to the aws management console
And type in the search Ec 2 and click on it
![1](![alt text](<img folder/pic-1.png>))

# And now in the Ec 2 dashboard 
click on launch instance 
![2](![alt text](<img folder/img 2.png>))

# And now name your server
And also choose ubuntu server and scroll down
![3](![alt text](<img folder/img 3.png>))

# After scrolling down you should see create key pair login
click on it 
![4](![alt text](<img folder/img 3.png>))

# Now in create key pair 
choose the name for your key pair and click on it then scroll down
![5](![alt text](<img folder/img5.png>))

# After scrolling down you should see network settings 
click on all the unchecked checkboxes then scroll down
![6](![alt text](<img folder/img 6.png>))

# After scrolling down you should see view all instances
click on it 
![7](![alt text](<img folder/img 7.png>))

# Now you should see actions,instance id,etc
click on instance id
![8](![alt text](<img folder/img 8.png>))

# Now in instance id 
click on conncet
1[9](![alt text](<img folder/img 9.png>))

# Now in connect
click on SSH client
![10](![alt text](<img folder/img 10.png>))

# Now in SSH client
copy the example link
![11](![alt text](<img folder/img 11.png>))

# Now go the folder your .pem file was downloaded and click on it and open with terminal
and now paste the link you copied
![12](![alt text](<img folder/Screen Shot 2024-08-19 at 20.30.58.png>))

# Go bact to the aws manangement console
![13](![alt text](<img folder/Img 14.png>))

# Now here click on search
And search elastic ip 
1[14](![alt text](<img folder/Screen Shot 2024-08-21 at 14.25.27.png>))

# And now in elastic ip 
click on allocate ip address
![15](![alt text](<img folder/img-16.png>))

# Then scroll down
keep all the settings unchanged and click allocate
![16](![alt text](<img folder/Screen Shot 2024-08-19 at 20.39.55.png>))

# then click on associate this elastic ip
![17](![alt text](< img folder/img18.png>))

# After clicking on it scroll down and  click on associate 
![18](![alt text](<img folder/15.png>))

# Install Nginx and Setup Your Website
Execute the following commands.

sudo apt update

sudo apt upgrade

sudo apt install nginx

Start your Nginx server by running the sudo systemctl start nginx command, enable it to start on boot by executing sudo systemctl enable nginx, and then confirm if it's running with the sudo systemctl status nginx command.
![19](![alt text](<img folder/Screen Shot 2024-08-19 at 21.32.12.png>))

# Go back to your EC2 dashboard and copy your Public IPv4 address.
![20](![alt text](<img folder/Screen Shot 2024-08-19 at 21.33.59.png>))

Visit your instances Public IPv4 address in a web browser to view the default Nginx startup page.
![21](![alt text](<img folder/Screen Shot 2024-08-19 at 21.34.11.png>))

Download your website template from your preferred website by navigating to the website, locating the template you want, and obtaining the download URL for the website.

## Go to tootplate website to get the website template to show on your website
And choose any template of your choice but i chose the barista cafe own click on it
![22](![alt text](<img folder/Screen Shot 2024-08-28 at 17.47.59.png>))

# After clicking on it
Scroll down to the download section, right-click to open the menu, and select Inspect from the options.
![23](![alt text](<img folder/Screen Shot 2024-08-28 at 18.00.18.png>))

# Select the Network tab.
![24](![alt text](<img folder/Screen Shot 2024-08-19 at 21.43.21.png>))

 # Click the Download button

 # After its done downloading
 in the network tab click on the zip file and choose copy and under copy choose copy url
 ![25](![alt text](<img folder/Screen Shot 2024-08-19 at 21.50.34.png>))

# Run this command sudo curl -o /var/www/html/2137_barista_cafe.zip https://www.tooplate.com/zip-templates/2137_barista_cafe.zip to download the websites file to your html directory.
![26](![alt text](<img folder/Screen Shot 2024-08-19 at 21.51.47.png>))


# To install the unzip tool, run the following command: sudo apt install unzip.
![27](![alt text](<img folder/Screen Shot 2024-08-19 at 21.56.09.png>))

# Navigate to the web server directory by running the following command: cd /var/www/html.

# Unzip the ocntents of your websites by running the command sudo unzip website template
![29](![alt text](<img folder/Screen Shot 2024-08-19 at 22.33.36.png>))

 # Update your nginx configuration by running the command sudo nano /etc/nginx/sites-available/default. Then, edit the root directive within your server block to point to the directory where your downloaded website content is stored.
 ![30](![alt text](<img folder/Screen Shot 2024-08-19 at 22.34.52.png>))

# edit the root directory ro the new one
![31](![alt text](<img folder/Screen Shot 2024-08-21 at 13.58.36.png>))

# Restart Nginx to apply the changes by running: sudo systemctl restart nginx.

 # Open a web browser and go to your Public IPv4 address/Elastic IP address to confirm that your website is working as expected.