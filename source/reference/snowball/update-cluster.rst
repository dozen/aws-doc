[ :ref:`aws <cli:aws>` . :ref:`snowball <cli:aws snowball>` ]

.. _cli:aws snowball update-cluster:


**************
update-cluster
**************



===========
Description
===========



While a cluster's ``ClusterState`` value is in the ``AwaitingQuorum`` state, you can update some of the information associated with a cluster. Once the cluster changes to a different job state, usually 60 minutes after the cluster being created, this action is no longer available.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/snowball-2016-06-30/UpdateCluster>`_


========
Synopsis
========

::

    update-cluster
  --cluster-id <value>
  [--role-arn <value>]
  [--description <value>]
  [--resources <value>]
  [--address-id <value>]
  [--shipping-option <value>]
  [--notification <value>]
  [--forwarding-address-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster-id`` (string)


  The cluster ID of the cluster that you want to update, for example ``CID123e4567-e89b-12d3-a456-426655440000`` .

  

``--role-arn`` (string)


  The new role Amazon Resource Name (ARN) that you want to associate with this cluster. To create a role ARN, use the `CreateRole <http://docs.aws.amazon.com/IAM/latest/APIReference/API_CreateRole.html>`_ API action in AWS Identity and Access Management (IAM).

  

``--description`` (string)


  The updated description of this cluster.

  

``--resources`` (structure)


  The updated arrays of  resources objects that can include updated  S3Resource objects or  LambdaResource objects.

  



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


  The updated shipping option value of this cluster's  ShippingDetails object.

  

  Possible values:

  
  *   ``SECOND_DAY``

  
  *   ``NEXT_DAY``

  
  *   ``EXPRESS``

  
  *   ``STANDARD``

  

  

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



``--forwarding-address-id`` (string)


  The updated ID for the forwarding address for a cluster. This field is not supported in most regions.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

