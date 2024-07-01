===============
Lab Environment 
===============

The notes are for the configurations on the test labs for practicals. I 
am also sharing the tools I use here. 

AWS Authentication and permissions
==================================

* Using the AWS Single Sign (SSO) to handle authentication. You may learn more about `AWS Identity Centre <https://aws.amazon.com/iam/identity-center/>`_. 
* In my case the lab role has already been created, not covering on this guide. 
* Configuring the profile for the lab example. 

  .. warning::

     It is not recommended to use administrator permissions. This is just 
     for learning purpose, in the below example `AWSAdministratorAccess` is 
     used.
 
  .. code-block:: bash
     
     aws configure sso

     SSO session name (Recommended): practicals
     SSO start URL [None]: https://d-xxxxxxxxxxxxx.awsapps.com/start
     SSO region [None]: af-south-1
     SSO registration scopes [sso:account:access]:
     Attempting to automatically open the SSO authorization page in your default browser.
     If the browser does not open or you wish to use a different device to authorize this request, open the following URL:

     https://device.sso.af-south-1.amazonaws.com/

     Then enter the code:

     XXXX-XXXX
     There are 3 AWS accounts available to you.
     Using the account ID xxxxxxxxxxxx
     There are 3 roles available to you.
     Using the role name "AWSAdministratorAccess"
     CLI default client Region [None]: af-south-1
     CLI default output format [None]: json
     CLI profile name [AWSAdministratorAccess-xxxxxxxxxxxx]: lab-profile


Infrastructure as Code
======================

* Using `AWS CDK <https://docs.aws.amazon.com/cdk/v2/guide/getting_started.html>`_ 
  with Go programming language. 
* Example of starting a CDK project. 
  
  .. code-block:: bash 

     # Installing aws-cdk
     npm install -g aws-cdk@2.147.2
     mkdir basic-cdk && cd basic-cdk
     # Initilize the go app and get dependancies
     cdk init app --language go
     go get
     go build
     cdk list 
     # Sythesize the CloudFormation template
     cdk synth
     # Testing the deployment, not adding resource just for testing project.
     cdk deploy BasicCdkStack --profile lab-profile
     # Destroying the created metadata and CloudFormation
     cdk destroy --profile lab-profile 

  .. note::

     The sample structure layout of the project. Also note the git environment 
     will also be created. So avoid nesting your projects. 

  .. code-block:: text 


     $ tree 

     ├── basic-cdk.go
     ├── basic-cdk_test.go
     ├── cdk.json
     ├── go.mod
     ├── go.sum
     └── README.md

Scripting and programming
=========================

* Using AWS SDK for Go

Design and diagrams 
===================

* Using `Draw.IO <https://app.diagrams.net/>`_ 