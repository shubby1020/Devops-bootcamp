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

# Create An A Record
To make your website accessible via your domain name rather than the IP address, you'll need to set up a DNS record. I did this by buying my domain from Namecheap and then moving hosting to AWS Route 53, where I set up an A record.

# note
I use godaddy for the domain name

# Type godaddy dashboard
click on the fisrt link
![32](![alt text](<img folder/Screen Shot 2024-08-29 at 17.13.32.png>))

# Then you will see domain name
click on the one you want to manage
![33](![alt text](<img folder/Screen Shot 2024-08-29 at 17.13.55.png>))

 # Go back to your AWS console, search for Route 53①, and then choose Route 53② from the list of services shown.
![34](![alt text](<img folder/Screen Shot 2024-08-29 at 17.15.28.png>))

# Click on Get started.
![35](![alt text](<img folder/Screen Shot 2024-08-29 at 17.15.28.png>))

# Select Create hosted zones① and click on Get started②.
![36](![alt text](<img folder/Screen Shot 2024-08-29 at 17.18.46.png>))

 # Enter your Domain name①, choose Public hosted zone② and then click on Create hosted zone③.
 ![37](![alt text](<img folder/Screen Shot 2024-08-29 at 17.19.52.png>))

 # Select the created hosted zone① and copy the assigned Values②.
 ![38](![alt text](<img folder/Screen Shot 2024-08-29 at 17.21.42.png>))

 #Paste the values you copied from Route 53 into the appropriate fields
 ![39](![alt text](<img folder/Screen Shot 2024-08-30 at 07.59.05.png>))

# Head back to your AWS console and click on Create record.
![40](![alt text](<img folder/Screen Shot 2024-08-29 at 17.21.42.png>))

 # Paste your Elastic IP address and then click on Create records.
![41](![alt text](<img folder/Screen Shot 2024-08-29 at 20.32.51.png>))

 # Your A record has been successfully created.
(![alt text](<img folder/Screen Shot 2024-08-29 at 20.32.51.png>))

# Click on create record again, to create the record for your sub domain.
(![alt text](<img folder/Screen Shot 2024-08-29 at 20.33.43.png>))

# Input the Record name(www➀), paste your IP address➁, and then click on Create records➂.

 # Open your terminal and run sudo nano /etc/nginx/sites-available/default to edit your settings. Enter your domain and subdomain names, then save the changes.
 (![alt text](image.png))


 # Restart your nginx server by running the sudo systemctl restart nginx command Then visit your websites

# install cetrbot to make your website secure
Install certbot by executing the following commands: sudo apt update sudo apt install certbot python3-certbot-nginx
(![alt text](image-1.png))

# Execute the sudo certbot --nginx command to request your certificate. Follow the instructions provided by certbot and select the domain name for which you would like to activate HTTPS.




