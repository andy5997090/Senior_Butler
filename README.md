# Senior_Butler
## Files and location
### We are using windows server in utd 
you should put source code in wwwroot file in :C/inetpub/wwwroot/
1. customer (subscriber) registration/login website (register folder)
2. provider registration/login website (Login folder)
3. Senior Butler website (Web Pages folder)
4. phpmyadmin folder is for controlling the database 
5. Database 
  1)	senior_butler.sql is the ideal database that we design for senior butler for future use. 
  2)	accounts.sql is the database that we currently using for our webpage. 

## Function of files

-	Read.php: This php file takes in the information from the secretary form submission (secretary.html). If no/some fields are left empty, read.php will output an error. Read.php will look for the customer ID, provider ID, and serviceNumber inputted in the form in the database and will output the related customer name, provider name, and service number.

-	register folder: you can access the register website by putting “localhost/register/index.php” or “seniorbutler.utdallas.edu/register/index.php” to access the registration website. The website will add the data into the database when it’s register. The information will be retrieved when the  login page is being used. 
    -	index.php : this is the homepage for the register
    -	register.php: register page 
    -	login.php: login page 
    -	logout.php: logout page 
    -	error.php: which shows the error 
    -	db.php: access the database 
    -	forgot.php: allow system to send the reset link to email  
    -	profile.php: show the profile page of the suer 
    -	reset_passoword.php: allow user to reset password when they forgot 
    -	veryfy.php: verify the user’s email
-	csvtest.html & csvtest2.php: add a new row of information to a csv file.
    -	csvtest.html: this html is used for the secretary to input the information. When he/she filled all the information required for dispatch (for now the fields on the html are according to the example survey we made on GoCanvas called “Inspection”, each apps require different fields to dispatch), then click submit and it will bring you to csvtest2.php.
    -	csvtest2.php: the function of this php is to add the information you inputted in csvtest.html into the CSV file located in the Data (:/inetpub/wwwroot/Data) folder. You will see “Successful” display on screen if it can add the data or “Failure” if it cannot. Make sure csvtest2.php has the correct path to the folder contains the CSV file, and also the permission of the folder allows you to read/write/delete the file inside the folder. If it does not work, please use Excel to create a new CSV file and input the heading for each column by hand because sometimes the sample dispatch CSV file you downloaded from the Gocanvas website is not working for csvtest2.php (maybe the csv file format from GoCanvas does not match with the php). 
-	Client1.html - is for client landing page.
-	Client2.html -is for client profile page to add their information such as name, address, phone number and some necessary information about the house.
-	Client3.html - is for client family member form where client can add their family members so they also get updated when any type of service is performed on the house. .
-	Client4.html - is for client package page, it shows what type of package client has.
-	Secretary.html - is for service schedule, secretary will input customer ID, provider ID and Service Number with date and time to see for what type of  service needs to be done.
-	Webpage1.html - is for Back office to create or edit profile for client. Beck office will be able to create profile for client. 
-	Webpage2.html - is for Back office landing page.
-	Webpage3.html - is for Back office to edit/update information of family members for client.
-	Webpage4.html- is for Back Office to edit/update information of location for client.
-	index.html - is for login page for provider/Back office.

## Software and Installation
### How to install GoCanvas:
For the dashboard part, you need to go to https://www.gocanvas.com/ and login.
For the mobile apps, you can download it from iOS App Store or Google Play Store. After that, you can login and see the apps you designed in the dashboard.

### GoCanvas Instruction
We used GoCanvas (https://www.gocanvas.com/) for the checklist function. When you log into GoCanvas, you can go to “Apps” and create apps there. We have made a “Inspection” apps for testing purpose. You can add different type of survey question into the apps. After you design and publish the checklist/survey, you should be able to see it in the GoCanvas mobile apps (available in both iOS and android - https://play.google.com/store/apps/details?id=com.gocanvas&hl=en).
There are a few functions we tested as well. You can upload some reference data to the GoCanvas dashboard by going to the “Reference Data & Images”, then add data into it. For example, you can add a list of existing customer to there and connect the file to the apps you want. In this way, the apps can have some pre-filled information. However, the data file must be a CSV Data file.
Another one is that after each survey submission, a pdf file will be generated. You can find them in “Submissions” and then choose the apps you want. After that, you should be able to see all the submission on that apps, and you can view or download the pdf file, or you can send the email to somebody else. We found out that the link for the pdf in the GoCanvas Dashboard requires GoCanvas login/account to read the pdf, while the link being attached in the email does not require login to see. Therefore, if you want the customer to read pdf without logging into GoCanvas, the link in the email is the one you want to save in the database or send to customers.
The last one is the dispatch function. In “Workflow & Dispatch”, you can send the survey to different workers for them to inspect customers home. You can create it one by one using create dispatch there, but we tried to use its upload dispatches function. And it requires preformatted CSV data file to do so. What you need to do is download “Sample Dispatch File”, you can see the format in the first row of the file, which is the same information required in the “create dispatch” in the GoCanvas website. You can fill in the information and upload that to the dashboard, and survey will be sent to the workers so they will know when and where do they need to work. However, it is inconvenient for the secretary to go into excel to add new column into the csv file, so we have written a html for a easier input. There is more detail belows about the html.
For the survey we are using now, which is called “Inspection”. We made a html website for the secretary to input the information, which is easier because he/she does not need to go into the CSV file and add information to each column. So how it work is: Open csvtest.html in :/inetpub/wwwroot/, then you can see all the field required to fill in. After you fill them in, click submit and it will go to csvtest2.php, which function is to add the information you inputted in csvtest.html into the CSV file located in the Data folder. You will see Successful if it can add the data or Failure if it cannot. If it does not work, please use Excel to create a new CSV file and input the heading for each column by hand because sometimes the sample dispatch CSV file you downloaded from the website is not working for csvtest2.php. And also make sure csvtest2.php has the correct path to the folder contains the CSV file, and also the permission of the folder allows you to read/write/delete the file inside the folder.

## MySQL:
Installer: https://dev.mysql.com/downloads/installer/
phpMyAdmin:
Installer: https://www.phpmyadmin.net/downloads/
To import the database into the virtual machine, you can use either the phpmyadmin or mySQL or the database application your chosen. Use the import function and select the file. 
To login, enter in the ID and password to see the database. 
ID: root
Password: 1234

### Web Pages/Web form:
1.	Download your favorite editor for example, visual studio code, sublime etc.. or it can be open on Notepad too.
2.	Go to the folder where html files are saved.
3.	Right click on file that you would like to open.
4.	Click on “open with” and it will show you options to open the file with your favorite editor/notepad/web browsers.
5.	Once the file code is open you can edit/delete/update the code.
6.	index.html - is for login page for provider/Back office.
7.	Client 1 - is for client landing page.
8.	Client 2 -is for client profile page.
9.	Client 3 - is for client family member form.
10.	Client4 - is for client package page
11.	Secretary - is for service schedule.
12.	Webpage 1 - is for Backoffice to create or edit profile for client.
13.	Webpage 2 - is for Backoffice landing page.
14.	Webpage3 - is for Backoffice to edit/update information of family members for client.
15.	Webpage4 - is for Backoffice to edit/update information of location for client.


Works:
1. Registration page: We are able to connect the database. Whenever the customers register, the information will be sent to the database. 
2. GoCanvas: We can create a inspection checklist and dispatch them into different workers. And we can also use the csvtest.html and csvtest2.php to create a formatted dispatch csv document and upload it to GoCanvas, so we do not need to dispatch it one by one on the website.
3. Senior Butler Website: There are four pages for clients and four pages for back office which includes the page for customer to update their information. Also, there is login form for back office/provider and secretary page for services.
4. The read.php file can read from the secretary.html - it takes the form submission and reads it against the database.
Doesn’t Work:
5. GoCanvas: We cannot save the pdf file/link into the database because it does not recognize which pdf file belongs to which customers.
6. There is no connection between the secretary confirmation page and sending of the csv file to the database
7. The web pages/web forms are not connected to the database including back office/provider login form; however, it could be connected the same way our registration page for clients are connected to the database. 


