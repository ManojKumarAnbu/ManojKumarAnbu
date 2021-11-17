 
Ex:N0  :3
Create Online Virtual Machine Using AWS

29/07/2021




AIM

To Create Virtual Machine online using Amazon web service.


PROCEDURE

1.   Enter the EC2 Dashboard

2.   Create and Configure Your Virtual Machine

3.   Click Launch Instance to Amazon EC2 console

4.   Click Select to Microsoft Windows Server 2012 R2 Base

5.   Click Review and Launch at the bottom of the page

6.   Create a Key Pair and Launch Your Instance

7.   Connect to Your Instance

8.   Select the Windows Server instance you just created and click Connect

9.   When prompted log in to the instance, use the User Name and Password you generated in to connect to your virtual machine.
10. Terminate Your Windows VM

11. Back on the EC2 Console, select the box next to the instance you created. Then click the

Actions button, navigate to Instante State, and click Terminate.

12. Confirm termination - select Yes, Terminate.
OUTPUT:





















Result:


Thus the given virtual machine using Amazon Web Service is created successfully.






 
Ex:N0  :4
Install Windows/Linux OS Using VMware Workstation/Oracle Virtual Box

12/08/2021



AIM

To create a Virtual Machine by installing VMware and add Window or Linux as Guest OS.


PROCEDURE

Create a new virtual machine. Open VMware Workstation click "Create a New Virtual
Machine".
Select type of configuration. A New Virtual Machine Wizard dialog box will be opened.
There are two options: typical and custom. Keep the default and click "Next" button.
Choose "Install disc image  file". This type matches the  iso file you download. Click
"Browse" to locate your Windows 7 iso file. Then, click "Next".
Select  the  version  of  Windows  to  install.  The  version  depends  on  the  iso  file  you download. You  can set your product key and personalize Windows later. Click "Next" button to continue.
Wait for the dialog to pop up. If you do not enter the Windows product key, click "Yes"
to continue.
Name the virtual machine. Change the name and location if you want. Click "Browse" to modify the path. Then, click "Next".
Specify Disk Capacity. Click the arrow button to change the maximum size of virtual machine's hard  disk. Also choose, store as one or more files on host computer. Click "Next" button to continue.
Confirm the setting. This step lists the settings the virtual machine will create. Click
"Customize Hardware" button to change any of the details.
Change Memory. If you want to change the memory of the virtual machine, select the arrow button or drag the slider tab. Click "Close" to go back to the last dialog box.
Create the new virtual machine. After confirming that the settings are all accurate, click the "Finish" button to start the process.

OUTPUT:















Result:

Thus the creation of  a Virtual Machine by installing VMware and add Window or Linux as Guest OS executed successfully.





Ex:N0  :5
Install a C Compiler in the Virtual Machine and Execute a Sample Program

19/08/2021




AIM:
 	To install a C Compiler in the virtual machine and execute a Sample C Program.

PROCEDURE:

Create a new virtual machine. Open VMware Workstation click "Create a New Virtual
Machine".
Select type of configuration. A New Virtual Machine Wizard dialog box will be opened.
There are two options: typical and custom. Keep the default and click "Next" button.
Choose "Install disc image  file". This type matches the iso file you download. Click
"Browse" to locate your Ubuntu iso file. Then, click "Next".
Select  the  version  of  Ubuntu  to  install.  The  version  depends  on  the  iso  file  you download. You  can set your product key and personalize Windows later. Click "Next" button to continue.
Wait for the dialog to pop up. If you do not enter the Windows product key, click "Yes"
to continue.
Name the virtual machine. Change the name and location if you want. Click "Browse" to modify the path. Then, click "Next".
Specify Disk Capacity. Click the arrow button to change the maximum size of virtual machine's hard  disk. Also choose, store as one or more files on host computer. Click "Next" button to continue.
Confirm the setting. This step lists the settings the virtual machine will create. Click
"Customize Hardware" button to change any of the details.
Change Memory. If you want to change the memory of the virtual machine, select the arrow button or drag the slider tab. Click "Close" to go back to the last dialog box.
Create the new virtual machine. After confirming that the settings are all accurate, click the "Finish" button to start the process.
In Ubuntu Guest OS check for gcc and install using the command “sudo apt gcc install” at the terminal.
Type a new file using any one of the text editor and type your first C program and save it.
 Using gcc compile the program in the current directory and show the results by executing ./a.out.



OUTPUT:







RESULT:
Thus the installation of c compile in the guest os and execution of a C program completed successfully.









Ex:N0  : 6
Install and Understand the Features of Own Cloud 

26/08/2021



AIM:
	To install and understand the features of Own Cloud.

PROCEDURE:

OwnCloud requires at least 128MB RAM but, recommended is 512 MB RAM, which should be increased according to number of users, files and activity. Also you will need a server with CentOS 7.x installed.  We will be using root account to run the commands, if you are logged in as non-root user, use sudo command at the start of the commands we are going to run. You may also run sudo su command to switch to root account.

1.Before installing any packages, it is recommended to update the system and packages, using following command.
    yum -y update

Now we will need to install LAMP stack in order to build up the required platform to install ownCloud. We will need to install Apache 2.4 with mod_php, PHP 5.4+ and MySQL/MariaDB.

2.To install Apache 2.4 run the following command.

    yum -y install httpd

3.Now start and enable it to automatically start at boot time using the following commands.

    systemctl start httpd
    systemctl enable httpd

4. ownCloud run on any PHP 5.4+ version, but PHP 5.4 is getting EOL, we will install PHP 5.5 on our server as recommended by ownCloud. Run the following commands to install PHP 5.5 on your system. PHP 5.5 is not available on default YUM repository, hence you will need to add SCL repositories too.

    yum -y install centos-release-scl
    yum -y install php55 php55-php php55-php-gd php55-php-mbstring php55-php-mysqlnd

5.Now restart Apache web server using the following command.

    systemctl restart httpd

6.Now install and setup Sendmail so that ownCloud can send push notifications using Sendmail. To install Sendmail run the following command.

    yum -y install sendmail
7.Now start Sendmail and enable it to start at boot time using following command.

    systemctl start sendmail
    systemctl enable sendmail

8. Now you will need to install MySQL/MariaDB, run the following command to do so.

    yum install mariadb mariadb-server

9.Now start and enable MariaDB to start automatically start at boot time using the following commands.

    systemctl start mariadb
    systemctl enable mariadb

10.Now secure your MariaDB installation using the following command.

    mysql_secure_installation

This will run a small script and ask for your current root password, as we have just installed MariaDB, so there is no root password, just leave it blank and proceed further to create a new root password for MariaDB server. It will further ask for removing anonymous user, sample database and it will ask if you want to disable remote login. Just hit enter for all question asked as we want to use the default choice for each question. This will configure and run our database server.

Once MariaDB server is ready we will need to create a database and database user for ownCloud. Login to your MariaDB command line interface, using the following command.

    mysql -u root -p

11.Now enter the password for root user which you have created during securing MySQL server. Once you are logged in, you will see following output.

    [root@Testbox ~]# mysql -u root -p
    Enter password:
    Welcome to the MariaDB monitor.  Commands end with ; or g.
    Your MariaDB connection id is 10
    Server version: 5.5.47-MariaDB MariaDB ServerCopyright (c) 2000, 2015, Oracle, MariaDB Corporation Ab and others.Type 'help;' or 'h' for help. Type 'c' to clear the current input statement.
MariaDB [(none)]&gt;

12.Create a database using following command.

   		 MariaDB [(none)]&gt; CREATE DATABASE owncloud;



13.Now create a database user using following command.

    MariaDB [(none)]&gt; GRANT ALL ON owncloud.* to 'ownclouduser'@'localhost' IDENTIFIED BY 'StrongPassword';

Be sure to change your database name and username and use a strong password replacing StrongPassword. Now reload the privileges table using following command.

    MariaDB [(none)]> FLUSH PRIVILEGES;
    MariaDB [(none)]> exit

14.As we have everything ready now, we can start the installation of ownCloud by running the following commands.

    rpm --import https://download.owncloud.org/download/ repositories/stable/ CentOS_7/ repodata/ repomd.xml.key

     wget http://download.owncloud.org/download/repositories/stable/CentOS_7/ce:stable.repo -O /etc/yum.repos.d/ce:stable.repo yum clean expire-cache yum -y install owncloud

This will download and install ownCloud in your server, you can find the ownCloud files in /var/www/owncloud directory.

15. Now you will need to fix some directories permissions so that ownCloud can manage the data on your server. Create a new file using any editor of your choice. In this tutorial we will be using nano, if you don't have nano installed, you can easily install it using yum -y install nano.

    nano ~/prm.sh

16.Now add the following lines of code into the script.

    #!/bin/bash
    ocpath='/var/www/html/owncloud'
    htuser='apache'
    htgroup='apache'
    rootuser='root'printf "Creating possible missing Directoriesn"
    mkdir -p $ocpath/data
    mkdir -p $ocpath/assets
    mkdir -p $ocpath/updaterprintf "chmod Files and Directoriesn"
    find ${ocpath}/ -type f -print0 | xargs -0 chmod 0640
    find ${ocpath}/ -type d -print0 | xargs -0 chmod 0750printf "chown Directoriesn"
    chown -R ${rootuser}:${htgroup} ${ocpath}/
    chown -R ${htuser}:${htgroup} ${ocpath}/apps/
    chown -R ${htuser}:${htgroup} ${ocpath}/assets/
    chown -R ${htuser}:${htgroup} ${ocpath}/config/
    chown -R ${htuser}:${htgroup} ${ocpath}/data/
    chown -R ${htuser}:${htgroup} ${ocpath}/themes/
    chown -R ${htuser}:${htgroup} ${ocpath}/updater/chmod +x ${ocpath}/occ
printf "chmod/chown .htaccessn" if [ -f ${ocpath}/.htaccess ] then chmod 0644 ${ocpath}/.htaccess chown ${rootuser}:${htgroup} ${ocpath}/.htaccess fi if [ -f ${ocpath}/data/.htaccess ] then chmod 0644 ${ocpath}/data/.htaccess chown ${rootuser}:${htgroup} ${ocpath}/data/.htaccess fi

Now save the file and exit the editor. 

17.Now make your file executable and run it using the following command.

    chmod 750 ~/prm.sh &amp;&amp; bash ~/prm.sh

You will see following output.

    [root@Testbox ~]# chmod 750 ~/prm.sh &amp;&amp; bash ~/prm.sh
    Creating possible missing Directories
    chmod Files and Directories
    chown Directories
    chmod/chown .htaccess

If you have SELinux enabled in your system, then you will need to adjust your SELinux module, otherwise you will get some permissions denied log messages. To check if you have SELinux enabled or not, run the following command.
                                                       sestatus
You will get output similar to this.

    SELinux status:                 enabled
    SELinuxfs mount:                /sys/fs/selinux
    SELinux root directory:         /etc/selinux
    Loaded policy name:             targeted
    Current mode:                   enforcing
    Mode from config file:          enforcing
    Policy MLS status:              enabled
    Policy deny_unknown status:     allowed
    Max kernel policy version:      28

On first line you will see the status of SELinux. If enabled run the following commands to adjust the SELinux permissions.

    semanage fcontext -a -t httpd_sys_rw_content_t '/var/www/html/owncloud/data'
    restorecon '/var/www/html/owncloud/data'
    semanage fcontext -a -t httpd_sys_rw_content_t '/var/www/html/owncloud/config'
    restorecon '/var/www/html/owncloud/config'
    semanage fcontext -a -t httpd_sys_rw_content_t '/var/www/html/owncloud/apps'
    restorecon '/var/www/html/owncloud/apps'
18. After settings appropriate SELinux configurations for the directories, you will need to run these commands so that ownCloud can connect other servers, also can can send notifications using Sendmail.

    setsebool -P httpd_can_network_connect on
    setsebool -P httpd_can_sendmail on

19.Now set up virtual hosts so that you can access ownCloud using your domain. Create a new file /etc/httpd/conf.d/owncloud.conf using your favorite text editor.

    nano /etc/httpd/conf.d/owncloud.conf

Add the following lines in the file.

      ServerName  MyCloud
      ServerName  your-domain.com
      DocumentRoot /var/www/html/owncloud/Alias /owncloud "/var/www/html/owncloud/"Options +FollowSymLinks
      AllowOverride AllDav offSetEnv HOME /var/www/html/owncloud
      SetEnv HTTP_HOME /var/www/html/owncloud

Make sure you change your-domain.com according to the domain you are going to use. Now save the file, exit from editor and restart Apache web server.

    systemctl restart httpd

20.Now you can access your ownCloud installation through front end using the domain you used during Virtual Host setup, if you have configured DNS. You can also access ownCloud using your server IP address.

    http://your-domain.com
                 Or
    http://Your-ServerIP
You will see following page.


21.Create a username and password for your administrator account. Next click on Storage and database link, and click on MySQL/MariaDB under Configure the database. Now provide database username, password and database name of the database, which you have created earlier. Click on Finish setup button once done.


22. Once the installation finishes you will see the following screen, you are now logged in to your ownCloud dashboard.


23. Securing own Cloud: You can use ownCloud over plain HTTP, but it is strongly recommended to use SSL/TLS to encrypt all of your server traffic, and to protect user’s logins and data in transit. You can use any SSL certificates to secure the traffic, for example self-signed certificate, Certbot or Let's Encrypt SSL or Enterprise SSL. For setting up Certbot or Let's Encrypt SSL, follow this guide.

Once you have a working SSL certificate, you can redirect all the traffic to HTTPS by editing your virtual hosts file, /etc/httpd/conf.d/owncloud.conf.

    nano /etc/httpd/conf.d/owncloud.conf
Now add the following line under virtual host.

    Redirect permanent / https://your-domain.com/
After editing your file should look like as shown below.

      ServerName  MyCloud
      ServerName  your-domain.com
      DocumentRoot /var/www/html/owncloud/
      Redirect permanent / https://your-domain.com/Alias /owncloud "/var/www/html/owncloud/"Options +FollowSymLinks
      AllowOverride AllDav offSetEnv HOME /var/www/html/owncloud
      SetEnv HTTP_HOME /var/www/html/owncloud
Administrators are encouraged to set the HTTP Strict Transport Security header, which asks browsers to not allow any connection to the ownCloud server using HTTP, and it attempts to prevent site visitors from bypassing invalid certificate warnings. To enable HSTS on your server, edit your Virtual Hosts file.

    nano /etc/httpd/conf.d/owncloud.conf
Now append the following lines into your file.

      ServerName your-domain.comHeader always set Strict-Transport-Security "max-age=15552000; includeSubDomains; preload"
Save the file and exit from editor. Now restart your Apache server using following command.

    systemctl restart httpd
Once you restart your server, all your HTTP requests will be sent to HTTPS, also HSTS will be enabled on your server too.


Note:
New sources for repository :
http://disq.us/url?url=http%3A%2F%2Fdownload.owncloud.org%2Fdownload%2Frepositories%2F10.0%2Fowncloud%2F%3ACfjhlkm-ljgy5ejUjqVxJuthDwU&cuid=3600920

or

http://download.owncloud.org/download/repositories/10.0/owncloud/











OUTPUT:
















Result:

Thus the Own Cloud setup installed successfully.





Ex:N0  :7
Create Developer Account in A CRM

09/09/2021



AIM:
To create developer account with the following specifications in a CRM.
Create objects and required fields to maintain the student database in cloud.
Create formula fields to calculate total marks, Grade and the result.
Apply validation rules when entering marks more than the certain criteria.

PROCEDURE:

Create a new Application “Student Marks” 
Label and Plural Label name : “Student Details”
Click Create App and then Goto My App Button
Create the Following Fields for the Object “Student Details”: 

Type objects in Quick find and select objects .click New Custom objects and Enter the following details : 


Create the Following Fields for the Object “Student Mark Details”: 

Type Apex class in Quick Find and click the new button : 
Type the Following Apex class code : 
/***
   	 Name          : StudentMarkDetails
 	 Created By    : Your Name 
Created date : Todaysdate   Description   : This custom controller is used to get the student mark details.

***/
public class StudentMarkDetails{

public Student_Mark_Detail__c studentMarks{get;set;}  //Getter setter variable to get the information

public StudentMarkDetails(){
    studentMarks = new Student_Mark_Detail__c();      //Instantiate the variable in constructor
}

public pagereference saveRecords(){            //This method will be called on click of save button.

    //This condition make sure the subject values are entered.
    if(studentMarks.Subject_1__c != null && studentMarks.Subject_2__c != null){    
        //Incase of any errors happen while inserting details, this block will catch the error and display in vf page.
        try{
              insert studentMarks;
              //On successfull insertion of details this will redirect to record details page.
              PageReference detailsPage = new PageReference('/' + studentMarks.id);
              return detailsPage;
        }
        catch(Exception e){
              ApexPages.addmessage(new ApexPages.message(ApexPages.severity.WARNING,+e.getMessage()));
              return null;
        }
    }
    else{
        ApexPages.addmessage(new ApexPages.message(ApexPages.severity.WARNING,'Please enter subject marks'));
        return null;
    }
    return null;
}
}
Click QuickSave and then save button.
Type pages  in Quick Find rightclick Visualforce pages and open it in new tab : 
Enter the Following details in VisualForce pages : 

Type the Following code in VisualForceMarkup: 
<apex:page controller="StudentMarkDetails">
  <apex:form >
  <apex:pageMessages ></apex:pageMessages>
      <apex:pageBlock title="Exam Details">
            <apex:pageBlockSection title="Please Enter Exam Marks" columns="1">
                  <apex:inputfield value="{!studentMarks.Name}"/>
                  <apex:inputfield value="{!studentMarks.Student__c}"/>
                  <apex:inputfield value="{!studentMarks.Subject_1__c}"/>
                  <apex:inputfield value="{!studentMarks.Subject_1_Staff_Name__c}"/>
                  <apex:inputfield value="{!studentMarks.Subject_2__c}"/>
                  <apex:inputfield value="{!studentMarks.Subject_2_Staff_Name__c}"/>
             </apex:pageBlockSection>
             <apex:pageBlockButtons >
                <apex:commandButton action="{!saveRecords}" value="Save"/>
            </apex:pageBlockButtons>
     </apex:pageBlock>
  </apex:form>
</apex:page>
Click Quick save .. and then click Save .
Type tabs in Quick Find and Click New in Visual Force Tabs and Enter the Following details as shown in the following snapshot and Click Save : 

Click Save Button


OUTPUT: 

Goto Student details tab and click New and Enter the required details : 

Click Save button 
Click the Enter Exam details tab : 
Enter the Required details : 

Click Save button 
In the final output you can see the total marks calculated : 

RESULT: 

Thus the creation of developer account in CRM is executed successfully.

Ex:N0  :8
Create a Warehouse Application in SalesForce.com

16/09/2021



AIM:
To create a Warehouse application in SalesForce.com

PROCEDURE:

This exercise covers the essential steps you need to follow to complete your first SalesForce application, in the “cloud.”.SalesForce.com best known for its CRM also provides a big and growing framework for cloud computing and applications.  With Force.com you can build apps faster, you can create applications without the concern of buying hardware or installing software.

Steps:
1.Starting at the Beginning
First of all you will need to register for a Salesforce.com developer account.  Once you have a valid username and password, login into SalesForce.com.

2. Salesforce Home Page
For this exercise you will create simple Warehouse application with the following objects:
Product
Fields: Name, Description, Price, Stock quantity
Line Item
Fields :Invoice #, Product #, Units sold, Total value
Invoice
Fields: Description, Invoice Value, Invoice Status

3. In the Product  object you will specify the Name, Description, Price and Total Inventory (stock) of the product. Creating an object automatically creates a table with each field as a column in the table. You can query that object using SOQL.

4. In the LineItem  in which you will specify the related Invoice Number, number of Units Sold and the Total amount.

5.Finally, in the Invoice  object in which you will specify a Description as well as the invoice Value and Status.

6.Creating the Objects
To create the objects go to Your user Name,  located in the upper-right corner of the Main page. Select Setup from the list.

The Personal Setup dialog will appear. Click on Create  and click on Objects

Personal Setup Dialog

In the next dialog click on the New Custom Object  button.
Custom Object Dialog

In the next dialog you are going to set the object properties.
Custom Object Dialog

Fill the property fields with the following information,
Label: Product
Plural Label: Products
Gender: Masculine
Object Name: Product (this is the name that will be used via API)
Record Name: Product Name
Data Type: Text

7.Creating Tabs
Check the option to Launch New Custom Tab Wizard  after saving this custom object.
Setup Menu

Then click the Save  button.
Setup Menu

You will see the next dialog, select the Tab Style  you prefer and click Next

Click Next  again and then click on Save

Now you will see the object definition detail. You need to create the custom field of that object. 

Click on New  under Custom Fields & Relationships

You will now create the Description Field so select  text  in the next dialog. Click on  Next

Input the information as shown in the next picture:
Click next again then click on  Save

8. Create a new Custom field, Price, and fill it in with the following information,
Data type: Number
Label: Price
Length: 18
Field Name: Price

9.Create a new Custom field, Total Inventory.
Data type: Number
Label: Total Inventory
ength:  18
Field Name: Total_Inventory
That is all you have to do on that object. Now you have to create the following objects following the same procedure.

10.Create the Line Item & Invoice Objects
Now you have to create the Line Item object.
Label: Line Item
Plural Label : Line Items
Gender: Masculine
Object Name: Line_Item (this is the name that will be used via API)
Record Name: Line Item Name
Data Type: Text

11.Create the Invoice object
Label: Invoice
Plural Label :Invoices
Gender: Masculine
Object Name: Invoice (this is the name that will be used via API)
Record Name: Invoice Name
Data Type: Auto Number
Display Format:  INV-{0} (this means that every invoice instance will have the INV
                                        prefix followed by an auto-increment number)

12.Creating Custom Fields
Now you will create some custom fields for the LineItem object and the Invoice object.
Go to objects and click on the Label Line Item

13.Create a new Custom field, Invoice.
Data type: Master-Detail
Related To: Invoice
Label: Invoice
Field Name: Invoice
Child Relationship Name: Line_Items

14.Create a new Custom field, Product.
Data type: Master-Detail
Related To: Product
Label: Product
Field Name: Product
Child Relationship Name: Line_Items

15. Create a new Custom field, Units Sold.
Data type: Number
Label: Units Sold
Length: 18
Field Name: Units_Sold

16.Create a new Custom field, Unit Price.
Data type: Number
Label: Unit price
Length: 18
Field Name: Unit_Price

17.Create a new Custom field, Total Value.
Data type: Formula
Label: Total Value
Field Name: Total_Value
Formula Return Type: Number
Total Value (number) = Units_Sold__c * Unit_Price__c

18.Now you will add the object fields for Invoice
Go to objects and click on the Label Invoice

Create a new Custom field, Description.
Data type: Text
Label: Description
Length: 255
Field Name: Description

19.Create a new Custom field, Invoice Status.
Data type: Picklist
Label: Invoice Status
In the text area type:
New Open Submitted
Field Name: Invoice_Status

20.Create a new Custom field, Total Invoice
Data type: Roll-up Summary
Summarized Object: Line Items
Select Roll-Up Type: SUM
Field to Aggregate: Total Value

Note: this roll-up summary will fetch all Line Items and SUM the total Value of the invoice.



RESULT:
Thus the first SalesForce.com application created successfully.




























Ex:N0  :9
Study and Install Apache Hadoop Framework

7/10/2021



AIM:
To study and install Apache Hadoop framework.


HADOOP
Hadoop is an open source framework for large-scale data processing. Hadoop enables companies to retain and make use of all the data they collect, performing complex analysis quickly and storing results securely over a number of distributed servers.
Traditional large-scale data processing was performed on a number of large computers. When demand increased, the enterprise would 'scale up', replacing existing servers with larger servers or storage arrays. The advantage of this approach was that the increase in the size of the servers had no affect on the overall system architecture. The disadvantage was that scaling up was expensive. Moreover, there's a limit on how much you can grow a system set up to process terabytes of information, and still keep the same system architecture. Sooner or later, when the amount of data collected becomes hundreds of terabytes or even petabytes, scaling up comes to a hard stop.
Scale-up strategies remain a good option for businesses that require intensive processing of data with strong internal cross-references and a need for transactional integrity. However, for growing enterprises that want to mine an ever-increasing flood of customer data, there is a better approach.
Using a Hadoop framework, large-scale data processing can respond to increased demand by "scaling out": if the data set doubles, you distribute processing over two servers; if the data set quadruples, you distribute processing over four servers. This eliminates the strategy of growing computing capacity by throwing more expensive hardware at the problem.
When individual hosts each possess a subset of the overall data set, the idea is for each host to work on their own portion of the final result independent of the others. In real life, it is likely that the hosts will need to communicate between each other, or that some pieces of data will be required by multiple hosts. This creates the potential for bottlenecks and increased risk of failure.
Therefore, designing a system where data processing is spread out over a number of servers means designing for self-healing distributed storage, fault-tolerant distributed computing, and abstraction for parallel processing. Since Hadoop is not actually a single product but a collection of several components, this design is generally accomplished through deployment of various components.
In addition to batch, interactive and real-time data access, the Hadoop "ecosystem" includes components that support critical enterprise requirements such as Security, Operations and Data Governance. To learn more about how critical enterprise requirements are implemented within the Hadoop ecosystem.
The project includes these modules:
Hadoop Common: The common utilities that support the other Hadoop modules.
Hadoop Distributed File System (HDFS™): A distributed file system that provides high-throughput access to application data.
Hadoop YARN: A framework for job scheduling and cluster resource management.
Hadoop MapReduce: A YARN-based system for parallel processing of large data sets.
Other Hadoop-related projects at Apache include:
Ambari™: A web-based tool for provisioning, managing, and monitoring Apache Hadoop clusters which includes support for Hadoop HDFS, Hadoop MapReduce, Hive, HCatalog, HBase, ZooKeeper, Oozie, Pig and Sqoop. Ambari also provides a dashboard for viewing cluster health such as heatmaps and ability to view MapReduce, Pig and Hive applications visually alongwith features to diagnose their performance characteristics in a user-friendly manner.
Avro™: A data serialization system.
Cassandra™: A scalable multi-master database with no single points of failure.
Chukwa™: A data collection system for managing large distributed systems.
HBase™: A scalable, distributed database that supports structured data storage for large tables.
Hive™: A data warehouse infrastructure that provides data summarization and ad hoc querying.
Mahout™: A Scalable machine learning and data mining library.
Pig™: A high-level data-flow language and execution framework for parallel computation.
Spark™: A fast and general compute engine for Hadoop data. Spark provides a simple and expressive programming model that supports a wide range of applications, including ETL, machine learning, stream processing, and graph computation.
Tez™: A generalized data-flow programming framework, built on Hadoop YARN, which provides a powerful and flexible engine to execute an arbitrary DAG of tasks to process data for both batch and interactive use-cases. Tez is being adopted by Hive™, Pig™ and other frameworks in the Hadoop ecosystem, and also by other commercial software (e.g. ETL tools), to replace Hadoop™ MapReduce as the underlying execution engine.
ZooKeeper™: A high-performance coordination service for distributed applications.
INSTALLATION
Prerequisites
	To use the Hortonworks Sandbox on Windows system must have the following
resources available:
1: Hosts
A 64-bit machine with a chip that supports virtualization. Not all 64-bit chips have this capability. Check your system documentation or your IT department. For more information, see this Microsoft article: http://windows.microsoft.com/en-us/windows7/32-bit-and-64-bit-windows-frequently-asked-questions
A BIOS that has been set to enable virtualization support. This is usually already set, but in some cases must be set manually.Check your system documentation or your IT department. For more information, see this Microsoft article:
http://www.microsoft.com/windows/virtual-pc/support/configurebios.aspx

2: Host Operating Systems:
Windows 7, 8

3: Supported Browsers:
Internet Explorer 9
Firefox – latest stable release
Google Chrome – latest stable release


4: At least 4 GB of RAM

Virtual Machine Environments:
Oracle VirtualBox, version 4.2 or later


Installing on Windows using Oracle VirtualBox

Open the Oracle VM VirtualBox Manager Double click:  

The Oracle VM Virtualization Manager window opens.


3. Change the Auto-Capture preference. File->Preferences and select
Input in the left navigation bar. Uncheck Auto-Capture Keyboard.

4. Import the Sandbox appliance file: File->Import Appliance


6. The Import Virtual Appliance screen opens




7. Click the Open appliance button; the file browser opens. Make sure to select the correct appliance. In this case, the top file is the VirtualBox formatted file. Click the Open button

8. You return to the Import Virtual Appliance screen. Click Next

9. The Appliance settings screen appears. The default settings work. If you have more then 4Gb of physical RAM installed, you may wish to allocate more RAM to the VM – 4GB of RAM in the Virtual Appliance will improve the performance. Click Import.


10. The appliance is imported.



11. Turn on the Sandbox. Select the appliance and click the green Start arrow. A console window opens and displays an information screen. Click OK to clear the info screen. 



Because what is being displayed is a conceptually separate machine, control of the mouse and the keyboard must be passed back and forth between the host and the VM. This is particularly useful when the VM has a GUI. In the case of the Sandbox appliance, however, you never need to use your keyboard or your mouse inside the Sandbox console window. If you accidently let the console “capture” your mouse or keyboard, you can release them back to the host machine by pressing the Ctrl key. Click OK.

12. Wait while the VM boots up. When the process is complete, the console
displays the login instructions for the Sandbox.

13. Use a browser on your host machine to open the URL displayed on the
console.





Result:

	Thus the Apache Hadoop Installation was studies successfully.

















Ex:N0  :10
MAP REDUCE Application

21/10/2021



AIM:
	To Configure a single node cluster using Hadoop framework and write a map reduce application

PROCEDURE:
Step 1: Installing Java
Java is the primary requirement for running hadoop on any system, So make sure you have Java installed on your system using following command


Step 2: Creating Hadoop User
We recommend to create a normal (nor root) account for hadoop working. So create a system account using following command.


After creating account, it also required to set up key based ssh to its own account. To do this use execute following commands.


Lets  verify key based login. Below command should not ask for password but first time it will prompt for adding RSA to the list of known hosts.


Step 3. Downloading Hadoop 2.6.0
Now download hadoop 2.6.0 source archive file using below command. You can also select alternate download mirror for increasing download speed.


Step 4. Configure Hadoop Pseudo-Distributed Mode
4.1. Setup Environment Variables
First we need to set environment variable uses by hadoop. Edit ~/.bashrc file and append following values at end of file.

Now apply the changes in current running environment

4.2. Edit Configuration Files
Hadoop has many of configuration files, which need to configure as per requirements of your hadoop infrastructure. Lets start with the configuration with basic hadoop single node cluster setup. first navigate to below location

Edit core-site.xml
<configuration>
<property>
  <name>fs.default.name</name>
    <value>hdfs://localhost:9000</value>
</property>
</configuration>
Edit hdfs-site.xml
<configuration>
<property>
 <name>dfs.replication</name>
 <value>1</value>
</property>

<property>
  <name>dfs.name.dir</name>
    <value>file:///home/hadoop/hadoopdata/hdfs/namenode</value>
</property>

<property>
  <name>dfs.data.dir</name>
    <value>file:///home/hadoop/hadoopdata/hdfs/datanode</value>
</property>
</configuration>
Edit mapred-site.xml
<configuration>
 <property>
  <name>mapreduce.framework.name</name>
   <value>yarn</value>
 </property>
</configuration>
Edit yarn-site.xml
<configuration>
 <property>
  <name>yarn.nodemanager.aux-services</name>
    <value>mapreduce_shuffle</value>
 </property>
</configuration>

4.3. Format Namenode
Now format the namenode using following command, make sure that Storage directory is
$ hdfs namenode -format

Step 5. Start Hadoop Cluster
Lets start your hadoop cluster using the scripts provides by hadoop. Just navigate to your hadoop sbin directory and execute scripts one by one.
$ cd $HADOOP_HOME/sbin/
Now run start-dfs.sh script.
$ start-dfs.sh
Sample output:
15/02/04 10:00:34 WARN util.NativeCodeLoader: Unable to load native-hadoop library for your platform... using builtin-java classes where applicable
Starting namenodes on [localhost]
localhost: starting namenode, logging to /home/hadoop/hadoop/logs/hadoop-hadoop-namenode-svr1.tecadmin.net.out
localhost: starting datanode, logging to /home/hadoop/hadoop/logs/hadoop-hadoop-datanode-svr1.tecadmin.net.out
Starting secondary namenodes [0.0.0.0]
The authenticity of host '0.0.0.0 (0.0.0.0)' can't be established.
RSA key fingerprint is 3c:c4:f6:f1:72:d9:84:f9:71:73:4a:0d:55:2c:f9:43.
Are you sure you want to continue connecting (yes/no)? yes
0.0.0.0: Warning: Permanently added '0.0.0.0' (RSA) to the list of known hosts.
0.0.0.0: starting secondarynamenode, logging to /home/hadoop/hadoop/logs/hadoop-hadoop-secondarynamenode-svr1.tecadmin.net.out
15/02/04 10:01:15 WARN util.NativeCodeLoader: Unable to load native-hadoop library for your platform... using builtin-java classes where applicable
Now run start-yarn.sh script.
$ start-yarn.sh
Sample output:
starting yarn daemons
starting resourcemanager, logging to /home/hadoop/hadoop/logs/yarn-hadoop-resourcemanager-svr1.tecadmin.net.out
localhost: starting nodemanager, logging to /home/hadoop/hadoop/logs/yarn-hadoop-nodemanager-svr1.tecadmin.net.out

Step 6. Access Hadoop Services in Browser
Hadoop NameNode started on port 50070 default. Access your server on port 50070 in your favorite web browser.
http://svr1.tecadmin.net:50070/


MAP-REDUCE ALGORITHM 
The input data can be divided into n number of chunks depending upon the amount of data and processing capacity of individual unit.
Next, it is passed to the mapper functions. Please note that all the chunks are processed simultaneously at the same time, which embraces the parallel processing of data.
After that, shuffling happens which leads to aggregation of similar patterns.
Finally, reducers combine them all to get a consolidated output as per the logic.
This algorithm embraces scalability as depending on the size of the input data, we can keep increasing the number of the parallel processing units.


Mapper Class
import java.io.IOException;
import org.apache.hadoop.io.IntWritable;
import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Mapper;
public class VoteCountMapper extends Mapper<Object, Text, Text, IntWritable>
 {
    private final static IntWritable one = new IntWritable(1);
    @Override
    public void map(Object key, Text value, Context output) throws IOException,
            InterruptedException {
        //If more than one word is present, split using white space.
        String[] words = value.toString().split(" ");
        //Only the first word is the candidate name
        output.write(new Text(words[0]), one);
    }
}
 
Reducer Class
import java.io.IOException;
import java.util.Iterator;
import org.apache.hadoop.io.IntWritable;
import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Reducer;
public class VoteCountReducer extends Reducer<Text, IntWritable, Text, IntWritable> {
    @Override
    public void reduce(Text key, Iterable<IntWritable> values, Context output)
            throws IOException, InterruptedException {
        int voteCount = 0;
        for(IntWritable value: values){
            voteCount+= value.get();
        }
        output.write(key, new IntWritable(voteCount));
    }
}

Main class
import org.apache.hadoop.conf.Configuration;
import org.apache.hadoop.conf.Configured;
import org.apache.hadoop.fs.Path;
import org.apache.hadoop.io.IntWritable;
import org.apache.hadoop.io.Text;
import org.apache.hadoop.mapreduce.Job;
import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;
import org.apache.hadoop.mapreduce.lib.input.TextInputFormat;
import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;
import org.apache.hadoop.mapreduce.lib.output.TextOutputFormat;
import org.apache.hadoop.util.Tool;
import org.apache.hadoop.util.ToolRunner;
public class VoteCountApplication extends Configured implements Tool{
    public static void main(String[] args) throws Exception {
        int res = ToolRunner.run(new Configuration(), new VoteCountApplication(), args);
        System.exit(res);       
    }
    @Override
    public int run(String[] args) throws Exception {
        if (args.length != 2) {
            System.out.println("usage: [input] [output]");
            System.exit(-1);
        }
        Job job = Job.getInstance(new Configuration());
        job.setOutputKeyClass(Text.class);
        job.setOutputValueClass(IntWritable.class);
        job.setMapperClass(VoteCountMapper.class);
        job.setReducerClass(VoteCountReducer.class);
        job.setInputFormatClass(TextInputFormat.class);
        job.setOutputFormatClass(TextOutputFormat.class);
        FileInputFormat.setInputPaths(job, new Path(args[0]));
        FileOutputFormat.setOutputPath(job, new Path(args[1]));
        job.setJarByClass(VoteCountApplication.class);
        job.submit();
        return 0;
    }
}

OUTPUT:
You can monitor the progress of the triggered job using Job Browser. If you wish, you could take a peek into the generated log files.


View Word Count Results
The final, consolidated vote count for each candidate can be found in a file present in the  directory/user/hue/VoteCountOutput. View this file using File Browser to know the number of votes each candidate got.





 RESULT:
	Thus the Map Reducer application executed successfully.
