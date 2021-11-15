# AWS Simple Storage Service (S3)
. jhjkkk
. kkllll
. hhjjj
## What is S3 :
    •	As its named it does the same. It allows you to store objects like images, data, backup, video, audio, etc. in a folder structure.
    •	It’s a cost effective storage solution charges $0.023 per/GB for storage
    •	Provides cheap, reliable, low latency and high throughput access 
    •	You can host a static website in an easy way
    •	It is well integrated with CloudWatch, SNS, SQS and Lambda which enable you to build an event driven application
    •	A bucket name is unique globally 
## S3 Limitations :
    o	Number of objects in a bucket : unlimited
    o	Maximum size of an object can be 5TB
    o	Maximum size of an object with 160GB can be uploaded using S3 console
    o	Object size larger than 5Gb and up to 5TB can be uploaded using multipart upload APIs with SDK, REST API and CLI
    o	Multipart size can vary from 5MB to 5GB and maximum number of parts can be 10,000
    o	With versioning enabled bucket if you upload an object with the same name then it will create another version instead of replacing the existing object
# S3 Storage Classes :
## Standard
    o	Default storage type
    o	Expensive than others
    o	No retrieval charge
    o	Min storage duration : NA
    o	Use case is for accessing on daily basis
    o	No retrieval charge or almost less
    o	Data stored in 3 different zones
    o	Provides high availability, durability and performance for frequently accessed data
    o	Durability is 99.999999999
    o	Availability is 99.99
    o	Data encryption at-rest and in-transit (SSL) 
## Standard IA (Infrequent Access )
    o	If you use the data 2-3 times on a month
    o	Retrieval charge is applied
    o	Min storage duration : 30
    o	Data stored in 3 different zones
    o	Designed for storing infrequent access data, but can be accessed faster when needed
    o	Storage cost is almost half of the standard tier
    o	Durability is 99.999999999
    o	Availability is 99.9
    o	Data encryption at-rest and in-transit (SSL)
    o	Data deleted within 30 days will be charged for entire 30 days
## One-Zone IA (Infrequent Access )
    o	Data stored only in one zone
    o	Cost is cheaper than standard IA
    o	Min storage duration : 30
    o	Designed for storing data that are accessed less frequently but can be accessed faster when needed
    o	Can be used to store secondary backup copies of on-premises data
    o	Durability is 99.999999999
    o	Availability is 99.5
    o	Important to remember that as its store data only in one zone if data lost cant be recovered
## Intelligent Tiering
    o	Data stored in 3 different zones
    o	No retrieval charge
    o	Monitoring and auto-tiering fees is applied per-object fees
    o	Min storage duration : 30
    o	Designed for optimizing cost by moving data automatically to the most cost effective access tier
    o	Durability is 99.999999999
    o	Availability is 99.9
    o	Provides similar performance as standard tier
    o	It stores data in two access tiers
    o	If any data is on IA and that data is accessed once then it moves back to the standard automatically
    o	Object less than 128 KB cannot be moved to IA
    o	It has no retrieval charge and no additional charges when data is moved between access tiers
## Reduced Redundancy Storage (Old)
    o	Designed to store noncritical, reproducible data at lower levels of redundancy than Amazon S3’s standard storage
    o	It does not replicate objects as many times as standard Amazon S3 storage.
    o	Durability is 99.99
    o	Availability is 99.99
## Glacier
    o	Use case is storing data for longer period
    o	Retrieval charge
    o	No cost for putting data
    o	Min storage duration : 90
    o	Data stored in 3 different zones
    o	Designed for secure, durable and cost effective archival storage
    o	It has three retrieval options starting from 1 minutes to hours
    o	Data can be uploaded directly to Glacier or by using storage life cycle policies
    o	Durability is 99.999999999
    o	Availability is 99.9
    o	Data encryption at-rest and in-transit (SSL)
## Glacier Deep Archive
    o	Most cheapest among all
    o	Use case is storing data for longest period
    o	Retrieval charge
    o	Min storage duration : 180
    o	No cost for putting data
    o	Data stored in 3 different zones
    o	Durability is 99.999999999
    o	Availability is 99.9
    o	Use case can be to store magnetic tape backups
    o	Retrieval time is within 12 hours
    o	Storage cost is up to 75% lesser than glacier storage tier
# 4-steps to follow
    o	Create bucket
    o	Configure options
    o	Permissions
    o	Upload file
# Object level logging
    o	To prevent deleting and overwriting of the objects to meet compliance
# CORS (Cross Origin Resource Sharing)
    o	CORS, is a security feature of modern web browsers.
    o	Useful when you are hosting a website
    o	CORS configuration is an XML file, which contains series of CORSRules and it can have up to 100 rules
    o	Sample CORS configuration file (https://docs.aws.amazon.com/sdk-for-javascript/v2/developer-guide/cors.html)
    o	Cross domain access
 
# S3 Delete Marker
    o	It is marker (key name/ version ID) for a versioned object that is named in a simple DELETE request. When you enable versioning on a bucket the object is not deleted but because of this marker S3 behaves as if it is deleted.
    o	It does not have data associated with it
    o	It is not associated with an ACL
# S3 Replication
# S3 Life Cycle
# Static Website Hosting (Policy)

      {
          "Version": "2012-10-17",
          "Statement": [
              {
                  "Effect": "Allow",
                  "Action": [
                      "s3:GetObject",
                      "s3:ListBucket",
                      "s3:List*",
                      "s3:PutBucket"
                  ],
                  "Resource": [
                      "arn:aws:s3:::batch2021-bucket/*",
                      "arn:aws:s3:::batch2021-bucket"
                  ]
              }
          ]
      }


# Important Links :
    •	https://aws.amazon.com/s3/features/access-points/#:~:text=Amazon%20S3%20Access%20Points%2C%20a,made%20through%20the%20access%20point.
    •	https://docs.aws.amazon.com/AmazonS3/latest/userguide/example-bucket-policies.html#example-bucket-policies-use-case-2
    •	https://aws.amazon.com/blogs/aws/introducing-amazon-s3-object-lambda-use-your-code-to-process-data-as-it-is-being-retrieved-from-s3/
    •	https://aws.amazon.com/s3/features/batch-operations/#:~:text=S3%20Batch%20Operations%20is%20a,data%20with%20a%20single%20request.
    •	https://docs.aws.amazon.com/AmazonS3/latest/userguide/EnableWebsiteHosting.html

# AWS CLI Reference Link :
    •	https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-profiles.html
    •	https://docs.aws.amazon.com/cli/latest/userguide/cli-services-ec2-instances.html
