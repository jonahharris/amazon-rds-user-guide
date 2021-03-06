# Determining Whether You Are Using the EC2\-VPC or EC2\-Classic Platform<a name="USER_VPC.FindDefaultVPC"></a>

Your AWS account and the region you select determines which of the two RDS platforms your DB instance is created on: *EC2\-Classic* or *EC2\-VPC*\. The type of platform determines if you have a default VPC, and which type of security group you use to provide access to your DB instance\. The legacy *EC2\-Classic* platform is the original platform used by Amazon RDS; if you are on this platform and want to use a VPC, you must create the VPC using the Amazon VPC console or Amazon VPC API\. Accounts that only support the *EC2\-VPC* platform have a default VPC where all DB instance are created, and you must use either an EC2 or VPC security group to provide access to the DB instance\.

**Note**  
If you are a new Amazon RDS customer, if you have never created a DB instance before, or if you are creating a DB instance in a region you have not used before, in almost all cases you are on the *EC2\-VPC* platform and have a default VPC\.

You can tell which platform your AWS account in a given region is using by looking at the dashboard on the RDS console or EC2 console\. If you are a new Amazon RDS customer, if you have never created a DB instance before, or if you are creating a DB instance in a region you have not used before, you might be redirected to the first\-run console page and will not see the home page following\.

If **Supported Platforms** indicates `VPC`, as shown following, your AWS account in the current region uses the *EC2\-VPC* platform, and uses a default VPC\. The name of the default VPC is shown below the supported platform\. To provide access to a DB instance created on the *EC2\-VPC* platform, you must create a VPC security group\. 

![\[EC2-VPC platform\]](http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/images/RDS-GSG-VPC.png)

If **Supported Platforms** indicates `EC2,VPC`, as shown following, your AWS account in the current region uses the *EC2\-Classic* platform, and you do not have a default VPC\. To provide access to a DB instance created on the* EC2\-Classic* platform, you must create a DB security group\. Note that you can create a VPC on the *EC2\-Classic* platform, but one is not created for you by default as it is on accounts that support the *EC2\-VPC* platform\. 

![\[EC2-Classic platform\]](http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/images/RDS-GSG-VPC0.png)

**Note**  
If you are interested in moving an existing DB instance into a VPC, you can use the AWS Management Console to do it easily\. For more information\. see [Moving a DB Instance Not in a VPC into a VPC](USER_VPC.WorkingWithRDSInstanceinaVPC.md#USER_VPC.Non-VPC2VPC)\. 