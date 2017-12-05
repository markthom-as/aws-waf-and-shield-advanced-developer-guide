# Setting Up for AWS WAF and AWS Shield<a name="setting-up-waf"></a>

This topic describes preliminary steps, such as creating an AWS account, to prepare you to use AWS WAF and AWS Shield Advanced\. You do not get charged to set up this account and other preliminary items\. You are only charged for AWS services that you use\. 

After you complete these steps, see [Getting Started with AWS WAF](getting-started.md) to continue getting started with AWS WAF\.

**Note**  
AWS Shield Standard is included with AWS WAF and does not require additional setup\. For more information, see [How AWS Shield Works](ddos-overview.md)\.

Before you use AWS WAF or AWS Shield Advanced for the first time, complete the following tasks:

+ [Step 1: Sign Up for an AWS Account](#setting-up-waf-aws-account)

+ [Step 2: Create an IAM User](#setting-up-waf-iam)

+ [Step 3: Download Tools](#setting-up-waf-tools)

## Step 1: Sign Up for an AWS Account<a name="setting-up-waf-aws-account"></a>

When you sign up for Amazon Web Services \(AWS\), your AWS account is automatically signed up for all services in AWS, including AWS WAF\. You are charged only for the services that you use\.

If you have an AWS account already, skip to the next task\. If you don't have an AWS account, use the following procedure to create one\.

**To sign up for AWS**

1. Open [https://aws\.amazon\.com/](https://aws.amazon.com/) and choose **Sign Up**\.

1. Follow the on\-page instructions\.

   Part of the sign\-up procedure involves receiving a phone call and entering a PIN using the phone keypad\.

Note your AWS account number, because you'll need it for the next task\.

## Step 2: Create an IAM User<a name="setting-up-waf-iam"></a>

To use the AWS WAF console, you must sign in to confirm that you have permission to perform AWS WAF operations\. You can use the root credentials for your AWS account, but we don't recommend it\. For greater security and control of your account, we recommend that you use AWS Identity and Access Management \(IAM\) to do the following:

+ Create an IAM user account for yourself or your business

+ Either add the IAM user account to an IAM group that has administrative permissions, or grant the IAM user account administrative permissions directly

You then can sign in to the AWS WAF console \(and other service consoles\) by using a special URL and the credentials for the IAM user\. You also can add other users to the IAM user account, and control their level of access to AWS services and to your resources\.

**Note**  
For information about creating access keys to access AWS WAF by using the [AWS Command Line Interface](http://aws.amazon.com/cli/) \(AWS CLI\), [Tools for Windows PowerShell](http://aws.amazon.com/documentation/powershell), the [AWS SDKs](http://aws.amazon.com/tools/), or the AWS WAF API, see [Managing Access Keys for IAM Users](http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html)\.

If you signed up for AWS but have not created an IAM user for yourself, you can create one using the IAM console\. If you aren't familiar with using the console, see [Working with the AWS Management Console](http://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/getting-started.html) for an overview\. 

**To create an IAM user for yourself and add the user to an Administrators group**

1. Use your AWS account email address and password to sign in to the [AWS Management Console](https://console.aws.amazon.com/) as the *[AWS account root user](http://docs.aws.amazon.com/IAM/latest/UserGuide/id_root-user.html)*\.

1. In the navigation pane of the console, choose **Users**, and then choose **Add user**\.

1. For **User name**, type ** Administrator**\.

1. Select the check box next to **AWS Management Console access**, select **Custom password**, and then type the new user's password in the text box\. You can optionally select **Require password reset** to force the user to select a new password the next time the user signs in\.

1. Choose **Next: Permissions**\.

1. On the **Set permissions for user** page, choose **Add user to group**\.

1. Choose **Create group**\.

1. In the **Create group** dialog box, type ** Administrators**\.

1. For **Filter**, choose **Job function**\.

1. In the policy list, select the check box for ** AdministratorAccess**\. Then choose **Create group**\.

1. Back in the list of groups, select the check box for your new group\. Choose **Refresh** if necessary to see the group in the list\.

1. Choose **Next: Review** to see the list of group memberships to be added to the new user\. When you are ready to proceed, choose **Create user**\.

You can use this same process to create more groups and users, and to give your users access to your AWS account resources\. To learn about using policies to restrict users' permissions to specific AWS resources, go to [Access Management](http://docs.aws.amazon.com/IAM/latest/UserGuide/access.html) and [Example Policies](http://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_examples.html)\.

To sign in as this new IAM user, first sign out of the AWS console\. Then use the following URL, where *your\_aws\_account\_id* is your AWS account number without the hyphens\. For example, if your AWS account number is `1234-5678-9012`, your AWS account ID is `123456789012`:

```
https://your_aws_account_id.signin.aws.amazon.com/console/
```

Enter the IAM user name and password that you just created\. When you're signed in, the navigation bar displays "*your\_user\_name* @ *your\_aws\_account\_id*"\.

If you don't want the URL for your sign\-in page to contain your AWS account ID, you can create an account alias\. From the IAM dashboard, choose **Customize** and enter an alias, such as your company name\. To sign in after you create an account alias, use the following URL:

```
https://your_account_alias.signin.aws.amazon.com/console/
```

To verify the sign\-in link for IAM users for your account, open the IAM console and check under the **IAM users sign\-in link** on the dashboard\. 

After you complete these steps, you can stop here and go to [Getting Started with AWS WAF](getting-started.md) to continue getting started with AWS WAF using the console\. If you want to access AWS WAF programatically using the AWS WAF API, continue on to the next step, [Step 3: Download Tools](#setting-up-waf-tools)\.

## Step 3: Download Tools<a name="setting-up-waf-tools"></a>

The AWS Management Console includes a console for AWS WAF, but if you want to access AWS WAF programatically, the following documentation and tools will help you:

+ If you want to call the AWS WAF API without having to handle low\-level details like assembling raw HTTP requests, you can use an AWS SDK\. The AWS SDKs provide functions and data types that encapsulate the functionality of AWS WAF and other AWS services\. To download an AWS SDK, see the applicable page, which also includes prerequisites and installation instructions:

  + [Java](https://aws.amazon.com/sdk-for-java/)

  + [JavaScript](http://aws.amazon.com/sdkforbrowser/)

  + [\.NET](https://aws.amazon.com/sdk-for-net/)

  + [Node\.js](https://aws.amazon.com/sdk-for-node-js/)

  + [PHP](https://aws.amazon.com/sdk-for-php/)

  + [Python](https://github.com/boto/boto)

  + [Ruby](https://aws.amazon.com/sdk-for-ruby/)

  For a complete list of AWS SDKs, see [Tools for Amazon Web Services](http://aws.amazon.com/tools/)\.

+ If you're using a programming language for which AWS doesn't provide an SDK, the [AWS WAF API Reference](http://docs.aws.amazon.com/waf/latest/APIReference/) documents the operations that AWS WAF supports\. 

+ The AWS Command Line Interface \(AWS CLI\) supports AWS WAF\. The AWS CLI lets you control multiple AWS services from the command line and automate them through scripts\. For more information, see [AWS Command Line Interface](https://aws.amazon.com/cli/)\.

+ AWS Tools for Windows PowerShell supports AWS WAF\. For more information, see [AWS Tools for Windows PowerShell Reference](http://aws.amazon.com/documentation/powershell/)\.