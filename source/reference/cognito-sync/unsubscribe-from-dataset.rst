[ :ref:`aws <cli:aws>` . :ref:`cognito-sync <cli:aws cognito-sync>` ]

.. _cli:aws cognito-sync unsubscribe-from-dataset:


************************
unsubscribe-from-dataset
************************



===========
Description
===========



Unsubscribes from receiving notifications when a dataset is modified by another device.

 

This API can only be called with temporary credentials provided by Cognito Identity. You cannot call this API with developer credentials.



========
Synopsis
========

::

    unsubscribe-from-dataset
  --identity-pool-id <value>
  --identity-id <value>
  --dataset-name <value>
  --device-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--identity-pool-id`` (string)


  A name-spaced GUID (for example, us-east-1:23EC4050-6AEA-7089-A2DD-08002EXAMPLE) created by Amazon Cognito. The ID of the pool to which this identity belongs.

  

``--identity-id`` (string)


  Unique ID for this identity.

  

``--dataset-name`` (string)


  The name of the dataset from which to unsubcribe.

  

``--device-id`` (string)


  The unique ID generated for this device by Cognito.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

