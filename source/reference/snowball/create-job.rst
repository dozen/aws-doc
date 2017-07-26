[ :ref:`aws <cli:aws>` . :ref:`snowball <cli:aws snowball>` ]

.. _cli:aws snowball create-job:


**********
create-job
**********



===========
Description
===========



Creates a job to import or export data between Amazon S3 and your on-premises data center. Your AWS account must have the right trust policies and permissions in place to create a job for Snowball. If you're creating a job for a node in a cluster, you only need to provide the ``clusterId`` value; the other job attributes are inherited from the cluster. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/snowball-2016-06-30/CreateJob>`_


========
Synopsis
========

::

    create-job
  [--job-type <value>]
  [--resources <value>]
  [--description <value>]
  [--address-id <value>]
  [--kms-key-arn <value>]
  [--role-arn <value>]
  [--snowball-capacity-preference <value>]
  [--shipping-option <value>]
  [--notification <value>]
  [--cluster-id <value>]
  [--snowball-type <value>]
  [--forwarding-address-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--job-type`` (string)


  Defines the type of job that you're creating. 

  

  Possible values:

  
  *   ``IMPORT``

  
  *   ``EXPORT``

  
  *   ``LOCAL_USE``

  

  

``--resources`` (structure)


  Defines the Amazon S3 buckets associated with this job.

   

  With ``IMPORT`` jobs, you specify the bucket or buckets that your transferred data will be imported into.

   

  With ``EXPORT`` jobs, you specify the bucket or buckets that your transferred data will be exported from. Optionally, you can also specify a ``KeyRange`` value. If you choose to export a range, you define the length of the range by providing either an inclusive ``BeginMarker`` value, an inclusive ``EndMarker`` value, or both. Ranges are UTF-8 binary sorted.

  



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


  Defines an optional description of this specific job, for example ``Important Photos 2016-08-11`` .

  

``--address-id`` (string)


  The ID for the address that you want the Snowball shipped to.

  

``--kms-key-arn`` (string)


  The ``kms-key-arn`` that you want to associate with this job. ``kms-key-arn`` s are created using the `CreateKey <http://docs.aws.amazon.com/kms/latest/APIReference/API_CreateKey.html>`_ AWS Key Management Service (KMS) API action.

  

``--role-arn`` (string)


  The ``role-arn`` that you want to associate with this job. ``RoleArn`` s are created using the `CreateRole <http://docs.aws.amazon.com/IAM/latest/APIReference/API_CreateRole.html>`_ AWS Identity and Access Management (IAM) API action.

  

``--snowball-capacity-preference`` (string)


  If your job is being created in one of the US regions, you have the option of specifying what size Snowball you'd like for this job. In all other regions, Snowballs come with 80 TB in storage capacity.

  

  Possible values:

  
  *   ``T50``

  
  *   ``T80``

  
  *   ``T100``

  
  *   ``NoPreference``

  

  

``--shipping-option`` (string)


  The shipping speed for this job. This speed doesn't dictate how soon you'll get the Snowball, rather it represents how quickly the Snowball moves to its destination while in transit. Regional shipping speeds are as follows:

   

   
  * In Australia, you have access to express shipping. Typically, Snowballs shipped express are delivered in about a day. 
   
  * In the European Union (EU), you have access to express shipping. Typically, Snowballs shipped express are delivered in about a day. In addition, most countries in the EU have access to standard shipping, which typically takes less than a week, one way. 
   
  * In India, Snowballs are delivered in one to seven days. 
   
  * In the US, you have access to one-day shipping and two-day shipping. 
   

  

  Possible values:

  
  *   ``SECOND_DAY``

  
  *   ``NEXT_DAY``

  
  *   ``EXPRESS``

  
  *   ``STANDARD``

  

  

``--notification`` (structure)


  Defines the Amazon Simple notification Service (Amazon SNS) notification settings for this job.

  



Shorthand Syntax::

    SnsTopicARN=string,JobStatesToNotify=string,string,NotifyAll=boolean




JSON Syntax::

  {
    "SnsTopicARN": "string",
    "JobStatesToNotify": ["New"|"PreparingAppliance"|"PreparingShipment"|"InTransitToCustomer"|"WithCustomer"|"InTransitToAWS"|"WithAWS"|"InProgress"|"Complete"|"Cancelled"|"Listing"|"Pending", ...],
    "NotifyAll": true|false
  }



``--cluster-id`` (string)


  The ID of a cluster. If you're creating a job for a node in a cluster, you need to provide only this ``clusterId`` value. The other job attributes are inherited from the cluster.

  

``--snowball-type`` (string)


  The type of AWS Snowball appliance to use for this job. Currently, the only supported appliance type for cluster jobs is ``EDGE`` .

  

  Possible values:

  
  *   ``STANDARD``

  
  *   ``EDGE``

  

  

``--forwarding-address-id`` (string)


  The forwarding address ID for a job. This field is not supported in most regions.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

JobId -> (string)

  

  The automatically generated ID for a job, for example ``JID123e4567-e89b-12d3-a456-426655440000`` .

  

  

