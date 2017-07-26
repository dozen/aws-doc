[ :ref:`aws <cli:aws>` ]

.. _cli:aws sts:


***
sts
***



===========
Description
===========

 

The AWS Security Token Service (STS) is a web service that enables you to request temporary, limited-privilege credentials for AWS Identity and Access Management (IAM) users or for users that you authenticate (federated users). This guide provides descriptions of the STS API. For more detailed information about using this service, go to `Temporary Security Credentials`_ . 

 

.. note::

  As an alternative to using the API, you can use one of the AWS SDKs, which consist of libraries and sample code for various programming languages and platforms (Java, Ruby, .NET, iOS, Android, etc.). The SDKs provide a convenient way to create programmatic access to STS. For example, the SDKs take care of cryptographically signing requests, managing errors, and retrying requests automatically. For information about the AWS SDKs, including how to download and install them, see the `Tools for Amazon Web Services page`_ . 

 

For information about setting up signatures and authorization through the API, go to `Signing AWS API Requests`_ in the *AWS General Reference* . For general information about the Query API, go to `Making Query Requests`_ in *Using IAM* . For information about using security tokens with other AWS products, go to `AWS Services That Work with IAM`_ in the *Using IAM* . 

 

If you're new to AWS and need additional technical information about a specific AWS product, you can find the product's technical documentation at `http\://aws.amazon.com/documentation/`_ . 

 

 **Endpoints**  

 

The AWS Security Token Service (STS) has a default endpoint of https://sts.amazonaws.com that maps to the US East (N. Virginia) region. Additional regions are available, but must first be activated in the AWS Management Console before you can use a different region's endpoint. For more information about activating a region for STS see `Activating STS in a New Region`_ in the *Using IAM* .

 

For information about STS endpoints, see `Regions and Endpoints`_ in the *AWS General Reference* .

 

 **Recording API requests**  

 

STS supports AWS CloudTrail, which is a service that records AWS calls for your AWS account and delivers log files to an Amazon S3 bucket. By using information collected by CloudTrail, you can determine what requests were successfully made to STS, who made the request, when it was made, and so on. To learn more about CloudTrail, including how to turn it on and find your log files, see the `AWS CloudTrail User Guide`_ .



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  assume-role
  assume-role-with-saml
  assume-role-with-web-identity
  decode-authorization-message
  get-federation-token
  get-session-token


.. _Activating STS in a New Region: http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_enable-regions.html
.. _Temporary Security Credentials: http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp.html
.. _AWS CloudTrail User Guide: http://docs.aws.amazon.com/awscloudtrail/latest/userguide/what_is_cloud_trail_top_level.html
.. _http\://aws.amazon.com/documentation/: http://aws.amazon.com/documentation/
.. _AWS Services That Work with IAM: http://docs.aws.amazon.com/IAM/latest/UserGuide/reference_aws-services-that-work-with-iam.html
.. _Tools for Amazon Web Services page: http://aws.amazon.com/tools/
.. _Regions and Endpoints: http://docs.aws.amazon.com/general/latest/gr/rande.html#sts_region
.. _Signing AWS API Requests: http://docs.aws.amazon.com/general/latest/gr/signing_aws_api_requests.html
.. _Making Query Requests: http://docs.aws.amazon.com/IAM/latest/UserGuide/IAM_UsingQueryAPI.html
