# Associating or Disassociating a Web ACL with a CloudFront Distribution or an Application Load Balancer<a name="web-acl-associating-cloudfront-distribution"></a>

To associate or disassociate a web ACL, perform the applicable procedure\. Note that you also can associate a web ACL with a CloudFront distribution when you create or update the distribution\. For more information, see [Using AWS WAF to Control Access to Your Content](http://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/distribution-web-awswaf.html) in the *Amazon CloudFront Developer Guide*\.

**Note**  
You can associate a web ACL with as many CloudFront distributions or Application Load Balancers as you want, but you can associate only one web ACL with a given distribution\.

**To associate a web ACL with a CloudFront distribution or Application Load Balancer**

1. Sign in to the AWS Management Console and open the AWS WAF console at [https://console\.aws\.amazon\.com/waf/](https://console.aws.amazon.com/waf/)\. 

1. In the navigation pane, choose **Web ACLs**\.

1. Choose the web ACL that you want to associate with a CloudFront distribution or Application Load Balancer\. 

1. On the **Rules** tab, under **AWS resources using this web ACL**, choose **Add association**\.

1. When prompted, use the **Resource** list to choose the CloudFront distribution or Application Load Balancer that you want to associate this web ACL with\. If you choose an Application Load Balancer, you also must specify a region\.

1. Choose **Add**\.

1. To associate this web ACL with additional CloudFront distributions or Application Load Balancers, repeat steps 4 through 6\.<a name="web-acl-disassociating-cloudfront-distribution-procedure"></a>

**To disassociate a web ACL from a CloudFront distribution or Application Load Balancer**

1. Sign in to the AWS Management Console and open the AWS WAF console at [https://console\.aws\.amazon\.com/waf/](https://console.aws.amazon.com/waf/)\. 

1. In the navigation pane, choose **Web ACLs**\.

1. Choose the web ACL that you want to disassociate from a CloudFront distribution or Application Load Balancer\.

1. On the **Rules** tab, under **AWS resources using this web ACL**, choose the **x** for each CloudFront distribution or Application Load Balancer that you want to disassociate this web ACL from\.