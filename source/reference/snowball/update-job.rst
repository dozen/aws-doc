[ :ref:`aws <cli:aws>` . :ref:`snowball <cli:aws snowball>` ]

.. _cli:aws snowball update-job:


**********
update-job
**********



===========
Description
===========



While a job's ``JobState`` value is ``New`` , you can update some of the information associated with a job. Once the job changes to a different job state, usually within 60 minutes of the job being created, this action is no longer available.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/snowball-2016-06-30/UpdateJob>`_


========
Synopsis
========

::

    update-job
  --job-id <value>
  [--role-arn <value>]
  [--notification <value>]
  [--resources <value>]
  [--address-id <value>]
  [--shipping-option <value>]
  [--description <value>]
  [--snowball-capacity-preference <value>]
  [--forwarding-address-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--job-id`` (string)


  The job ID of the job that you want to update, for example ``JID123e4567-e89b-12d3-a456-426655440000`` .

  

``--role-arn`` (string)


  The new role Amazon Resource Name (ARN) that you want to associate with this job. To create a role ARN, use the `CreateRole <http://docs.aws.amazon.com/IAM/latest/APIReference/API_CreateRole.html>`_ AWS Identity and Access Management (IAM) API action.

  

``--notification`` (structure)


  The new or updated  notification object.

  



Shorthand Syntax::

    SnsTopicARN=string,JobStatesToNotify=string,string,NotifyAll=boolean




JSON Syntax::

  {
    "SnsTopicARN": "string",
    "JobStatesToNotify": ["New"|"PreparingAppliance"|"PreparingShipment"|"InTransitToCustomer"|"WithCustomer"|"InTransitToAWS"|"WithAWS"|"InProgress"|"Complete"|"Cancelled"|"Listing"|"Pending", ...],
    "NotifyAll": true|false
  }



``--resources`` (structure)


  The updated  S3Resource object (for a single Amazon S3 bucket or key range), or the updated  resources object (for multiple buckets or key ranges). 

  



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



``--address-id`` (string)


  The ID of the updated  Address object.

  

``--shipping-option`` (string)


  The updated shipping option value of this job's  ShippingDetails object.

  

  Possible values:

  
  *   ``SECOND_DAY``

  
  *   ``NEXT_DAY``

  
  *   ``EXPRESS``

  
  *   ``STANDARD``

  

  

``--description`` (string)


  The updated description of this job's  JobMetadata object.

  

``--snowball-capacity-preference`` (string)


  The updated ``SnowballCapacityPreference`` of this job's  JobMetadata object. The 50 TB Snowballs are only available in the US regions.

  

  Possible values:

  
  *   ``T50``

  
  *   ``T80``

  
  *   ``T100``

  
  *   ``NoPreference``

  

  

``--forwarding-address-id`` (string)


  The updated ID for the forwarding address for a job. This field is not supported in most regions.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

