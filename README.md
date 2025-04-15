The Process-

1.Create two users User01 and User02 in the Azure AD and give them Global Admin Access.

Go to Azure Portal and Select Azure Active Directory.
 

Click on Add and Select User to Create User01.

 

Fill the Details such as username,password etc.
 
Click on Roles and Select Global Administrator.

 
Fill the other details and click Create.

 
Wait for the Notification to Shows Up.

 

Similarly Create User02 While repeating the same steps.
 

 

 

 
2.Both User 01 and User 02 are owners for the subscription.
Go to Azure Portal and Select Subscriptions and click on your subscription. 
 
Go to Access Control(IAM) and click add.
 

Select Add role assignment.

 
Select Owner as Role and enter details of the two users.

 

Click Save.
 
Wait For the notification to Pop Up.
 

3.Create User03 and provide it the reader access. Can this User create the VM in the Subscription?

Create a New User named User03.
 
In Roles Select Global Reader Role.
 

Fill the rest of the details and click create.
 

Wait for the notification to Pop up
 


The Portal Will not Let User03 create a VM since it only has a reader role.


4.Create two servers in the Main Office and place them in one Availability Set.

Log Back Into Global Admin Account and Click Create a virtual machine to Create the Server.
 
Fill the Details and Place it in the Availability Set standard_B1ms.
 

Fill in the rest of the details and click Create.
 




Wait for Notification to Pop up.

 

Similarly Create the Second VM Server.

 




Select the same Availability set as the first server i.e. standard_B1ms.

 

Fill in the rest of the details and click create.

 


Wait for Notification.

 

Check if they are in Same Availability Set or not.

 


5.Create a policy for the VM Size and Location.

Go to Azure Portal and Select Policy and Click on Definitions and the Policy Definition.

 

Fill in the Details for the Policy.
 
Make Necessary Changes to the Code according to policy requirements and Select Assign to select which resources or subscription this policy will apply to.
 

 
 


 

 


6.Validate the policy after its creation.

Try to Create a Resource Group in any region other than the Central US.

 
Try To Create a New VM in a Region other than the Central US.
 

 




 

7.Create and apply the “Lock” at the Resource Group Level so that all the corresponding resources will be Locked.

Go to Azure Portal and Select Resource Groups and click on a resource group.

 
Go to the Locks section and click +add.

 

Select the details of the lock such as name,type and click add.

 

 

8.Create Storage Account and Give access to the respective Client IP Address only.

Go to Storage Accounts in Azure Portal and Click Create a Storage Account.
 

Fill the necessary details and click create.

 

Wait for notification to show Deployment is complete.

 


9.Understand the Difference Between Availability Set and Zone.


Availability Set-
An availability set is a logical grouping of VMs.By deploying at least two virtual machines into an availability set,we ensure that at least one of them remains available whenever planned or unplanned maintenance occurs.
Deploying VMs in an availability set will not protect an application from failures that are application-specific,it will provide protection against network outages, physical hardware failures, and power interruptions within an Azure data center. 

Availability Zone-
An availability zone is a unique physical location that exists within a region.Every availability zone contains at least one data center within the region. Each of these data centers has its own infrastructure. Every enabled region in Azure consists of at least three separate zones that are physically separated so that it protects applications from data center failures.
Difference Between Availability Set and Availability Zone-
●	Availability zones are similar in concept to availability sets. However, there is a distinct difference. While availability sets are used to protect applications from hardware failures within an Azure data center, availability zones protect applications from complete Azure data center failures.
●	From the Service Level Agreement (SLA) standpoint, i.e uptime and connectivity - With Availability Set azure offers 99.95% SLA whereas with Availability Zone we have 99.99% SLA. 



 

