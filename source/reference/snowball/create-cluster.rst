[ :ref:`aws <cli:aws>` . :ref:`snowball <cli:aws snowball>` ]

.. _cli:aws snowball create-cluster:


**************
create-cluster
**************



===========
Description
===========



Creates an empty cluster. Each cluster supports five nodes. You use the  create-job action separately to create the jobs for each of these nodes. The cluster does not ship until these five node jobs have been created.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/snowball-2016-06-30/CreateCluster>`_


========
Synopsis
========

::

    create-cluster
  --job-type <value>
  --resources <value>
  [--description <value>]
  --address-id <value>
  [--kms-key-arn <value>]
  --role-arn <value>
  [--snowball-type <value>]
  --shipping-option <value>
  [--notification <value>]
  [--forwarding-address-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--job-type`` (string)


  The type of job for this cluster. Currently, the only job type supported for clusters is ``LOCAL_USE`` .

  

  Possible values:

  
  *   ``IMPORT``

  
  *   ``EXPORT``

  
  *   ``LOCAL_USE``

  

  

``--resources`` (structure)


  The resources associated with the cluster job. These resources include Amazon S3 buckets and optional AWS Lambda functions written in the Python language. 

  



JSON Syntax::

  {
    "S3Resources": [
      {
        "BucketArn": "string",
        "KeyRange": {
          "BeginMarker": "string",
          "EndMarker": "string"
        }
      }
      ...
    ],
    "LambdaResources": [
      {
        "LambdaArn": "string",
        "EventTriggers": [
          {
            "EventResourceARN": "string"
          }
          ...
        ]
      }
      ...
    ]
  }



``--description`` (string)


  An optional description of this specific cluster, for example ``Environmental Data Cluster-01`` .

  

``--address-id`` (string)


  The ID for the address that you want the cluster shipped to.

  

``--kms-key-arn`` (string)


  The ``kms-key-arn`` value that you want to associate with this cluster. ``kms-key-arn`` values are created by using the `CreateKey <http://docs.aws.amazon.com/kms/latest/APIReference/API_CreateKey.html>`_ API action in AWS Key Management Service (AWS KMS). 

  

``--role-arn`` (string)


  The ``role-arn`` that you want to associate with this cluster. ``RoleArn`` values are created by using the `CreateRole <http://docs.aws.amazon.com/IAM/latest/APIReference/API_CreateRole.html>`_ API action in AWS Identity and Access Management (IAM).

  

``--snowball-type`` (string)


  The type of AWS Snowball appliance to use for this cluster. Currently, the only supported appliance type for cluster jobs is ``EDGE`` .

  

  Possible values:

  
  *   ``STANDARD``

  
  *   ``EDGE``

  

  

``--shipping-option`` (string)


  The shipping speed for each node in this cluster. This speed doesn't dictate how soon you'll get each Snowball Edge appliance, rather it represents how quickly each appliance moves to its destination while in transit. Regional shipping speeds are as follows:

   

   
  * In Australia, you have access to express shipping. Typically, appliances shipped express are delivered in about a day. 
   
  * In the European Union (EU), you have access to express shipping. Typically, Snowball Edges shipped express are delivered in about a day. In addition, most countries in the EU have access to standard shipping, which typically takes less than a week, one way. 
   
  * In India, Snowball Edges are delivered in one to seven days. 
   
  * In the US, you have access to one-day shipping and two-day shipping. 
   

  

  Possible values:

  
  *   ``SECOND_DAY``

  
  *   ``NEXT_DAY``

  
  *   ``EXPRESS``

  
  *   ``STANDARD``

  

  

``--notification`` (structure)


  The Amazon Simple notification Service (Amazon SNS) notification settings for this cluster.

  



Shorthand Syntax::

    SnsTopicARN=string,JobStatesToNotify=string,string,NotifyAll=boolean




JSON Syntax::

  {
    "SnsTopicARN": "string",
    "JobStatesToNotify": ["New"|"PreparingAppliance"|"PreparingShipment"|"InTransitToCustomer"|"WithCustomer"|"InTransitToAWS"|"WithAWS"|"InProgress"|"Complete"|"Cancelled"|"Listing"|"Pending", ...],
    "NotifyAll": true|false
  }



``--forwarding-address-id`` (string)


  The forwarding address ID for a cluster. This field is not supported in most regions.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ClusterId -> (string)

  

  The automatically generated ID for a cluster.

  

  

