# AWS
My journey to learning and understanding AWS.

**2020-06-13:** Successfully passed the AWS Certified Solutions Architect – Associate exam  [Link](https://www.youracclaim.com/badges/ad704ac3-49aa-4e13-9fd8-aa95f7cde3ae/linked_in)

# Personal Website Project - [Link](https://benJDtom.com)
### Goal
Host a basic website featuring information about me, my projects and contact information on how I can be reached in AWS using the Well Architectured Framework approach.

This website should be quick to load, resilient to AZ failures and scalable to meet any demand.
### Inital Consderations
There are many services that could host a website in AWS, including the following:
* EC2 Instances
* ECS Containers
* Lightsail
* S3 Bucket

### Relevant AWS Documentation
* [AWS Websites](https://aws.amazon.com/websites/)
* [Building Static Websits on AWS Whitepaper](http://d0.awsstatic.com/whitepapers/Building%20Static%20Websites%20on%20AWS.pdf)
* [Hosting a Static Website on Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/WebsiteHosting.html)
* [Logging Web Traffic](https://docs.aws.amazon.com/AmazonS3/latest/dev/LoggingWebsiteTraffic.html)
* [Contact Form for S3 Static Websites](https://aws.amazon.com/blogs/architecture/create-dynamic-contact-forms-for-s3-static-websites-using-aws-lambda-amazon-api-gateway-and-amazon-ses/)

## Well Architectured Framework Planning
### Operational Excellence
 I would like to implement traffic logging to see how heavy the load is on the website and monitor where traffic is coming from to ensure everything is working correctly and as intended.
### Security
This website will contain minimal personal information about myself, so some form of security would be ideal. I would like to implement geo-fencing to keep traffic limited to Canada and the United States, as I don't see a need for my content to be accessed in any other countries at this time. I want the website to only allow traffic from CloudFront through HTTPS, and not let traffic to the bucket or any unencrypted HTTP traffic.
### Reliability
As this website will not be bussiness critical; reliability is not one of my biggest concerns, but I want the ability to fail over accross availability zones. I would also like to outline(although not implement) a possible disaster recovery plan for my final implenmtation. 
### Performance Efficiency
Performance is one of my more ambitious goals in this project, as for a site this small and simple no performance optimizations should be needed, but I hope to learn and utilize AWS Cloudfront to make load times nearly instant.
### Cost Optimization
To keep costs down and achieve cost optimization, I am planning to use an S3 bucket rather than one of the other services mentioned above, as an S3 bucket allows the website to be unhinged from traffic-associated costs.

## Outline
Service     |Function                                                        |Estimated Costs
------------|----------------------------------------------------------------|-------------
S3          | Store website files and serve content                          |$1 Yearly
Route 53    | Domain registrar, DNS handling, routing & geo-fencing          |$12 Yearly
CloudFront  | Maintain a cache of the website and improve load times         |$2 Yearly
API Gateway | Handle incoming contact forms via restful API, pass to Lambda  |¢50 Yearly
Lambda      | Generate email with contact form information                   |$1 Yearly
SES         | Send emails generated by Lambda                                |$1 Yearly
&nbsp;      | &nbsp;                                                         |**Total: $17.50/year**

## Build & Test

DISCLAIMER: I am not a developer, and give all credit for the template to HTML5UP ([Link](https://html5up.net/read-only))
1. In Route 53 purchase the website you wish to use for the static website (In this case benjdtom.com)
![domain](/images/domain.png)
2. Create an S3 bucket for the website
![bucket](/images/bucket.png)
3. Ensure that static website hosting is enabled and setup for the bucket
![hosting](/images/hosting.png)

# AWS Docs & Links
## Docs
* [AWS Well Architected Framework](https://d1.awsstatic.com/whitepapers/architecture/AWS_Well-Architected_Framework.pdf)
* [CloudFormation Basics](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/gettingstarted.templatebasics.html)

## Links
* [Pricing Calculator](https://calculator.aws/#/)
