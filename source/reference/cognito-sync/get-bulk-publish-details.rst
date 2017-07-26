[ :ref:`aws <cli:aws>` . :ref:`cognito-sync <cli:aws cognito-sync>` ]

.. _cli:aws cognito-sync get-bulk-publish-details:


************************
get-bulk-publish-details
************************



===========
Description
===========



Get the status of the last bulk-publish operation for an identity pool.

 

This API can only be called with developer credentials. You cannot call this API with the temporary user credentials provided by Cognito Identity.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-sync-2014-06-30/GetBulkPublishDetails>`_


========
Synopsis
========

::

    get-bulk-publish-details
  --identity-pool-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--identity-pool-id`` (string)
A name-spaced GUID (for example, us-east-1:23EC4050-6AEA-7089-A2DD-08002EXAMPLE) created by Amazon Cognito. GUID generation is unique within a region.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

IdentityPoolId -> (string)

  A name-spaced GUID (for example, us-east-1:23EC4050-6AEA-7089-A2DD-08002EXAMPLE) created by Amazon Cognito. GUID generation is unique within a region.

  

BulkPublishStartTime -> (timestamp)

  The date/time at which the last bulk publish was initiated.

  

BulkPublishCompleteTime -> (timestamp)

  If BulkPublishStatus is SUCCEEDED, the time the last bulk publish operation completed.

  

BulkPublishStatus -> (string)

  Status of the last bulk publish operation, valid values are: 

  NOT_STARTED - No bulk publish has been requested for this identity pool

   

  IN_PROGRESS - Data is being published to the configured stream

   

  SUCCEEDED - All data for the identity pool has been published to the configured stream

   

  FAILED - Some portion of the data has failed to publish, check FailureMessage for the cause.

  

  

FailureMessage -> (string)

  If BulkPublishStatus is FAILED this field will contain the error message that caused the bulk publish to fail.

  

