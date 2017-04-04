## The basic infrastructure in only five minutes
As a first step, we will set up the basic infrastructure. 


## How to start asap?
1. [Create an IAM User and setup the aws cli](http://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-set-up.html)
1. Create a key called "keyToSuccess" in the [webinterface](https://console.aws.amazon.com/console/home) -> EC2 -> Key Pairs -> *Create Key Pair*
1. [Download the template](cf_template/template.json)
1. Open a terminal and insert:
```bash
aws cloudformation create-stack --region us-east-1 --stack-name theStackIsBack --template-body file:///Users/PATH_TO_TEMPLATE/template.json --parameters ParameterKey=KeyName,ParameterValue=keyToSuccess ParameterKey=DBName,ParameterValue=TheDbName ParameterKey=DBPwd,ParameterValue=Th3P455w0rd ParameterKey=DBUser,ParameterValue=TheDbUser
```

## Infrastructure 
![simple_mockup](../../documentation/images/infrastructure_basic.png)

## Description
At this point you should you habe the following created AWS resources:

- *Elastic Compute Cloud (EC2)*, two virtual Linux servers called Amazon Linux. The SpringBoot application with the embedded Tomcat Server will be installed on each virtual server whit help of AWS CodePipeline.
- *Relational Database Service (RDS)* providing a MySQL database. The Spring Boot application relies on this database.

**Next: [Description of the basic template](../../documentation/template-desc.md)**