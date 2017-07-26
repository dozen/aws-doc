[ :ref:`aws <cli:aws>` . :ref:`cognito-sync <cli:aws cognito-sync>` ]

.. _cli:aws cognito-sync subscribe-to-dataset:


********************
subscribe-to-dataset
********************



===========
Description
===========



Subscribes to receive notifications when a dataset is modified by another device.

 

This API can only be called with temporary credentials provided by Cognito Identity. You cannot call this API with developer credentials.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-sync-2014-06-30/SubscribeToDataset>`_


========
Synopsis
========

::

    subscribe-to-dataset
  --identity-pool-id <value>
  --identity-id <value>
  --dataset-name <value>
  --device-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--identity-pool-id`` (string)


  A name-spaced GUID (for example, us-east-1:23EC4050-6AEA-7089-A2DD-08002EXAMPLE) created by Amazon Cognito. The ID of the pool to which the identity belongs.

  

``--identity-id`` (string)


  Unique ID for this identity.

  

``--dataset-name`` (string)


  The name of the dataset to subcribe to.

  

``--device-id`` (string)


  The unique ID generated for this device by Cognito.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

