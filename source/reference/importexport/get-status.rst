[ :ref:`aws <cli:aws>` . :ref:`importexport <cli:aws importexport>` ]

.. _cli:aws importexport get-status:


**********
get-status
**********



===========
Description
===========

This operation returns information about a job, including where the job is in the processing pipeline, the status of the results, and the signature value associated with the job. You can only return information about jobs you own.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/importexport-2010-06-01/GetStatus>`_


========
Synopsis
========

::

    get-status
  --job-id <value>
  [--api-version <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--job-id`` (string)
A unique identifier which refers to a particular job.

``--api-version`` (string)
Specifies the version of the client tool.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command returns the status the specified job::

  aws importexport get-status  --job-id EX1ID

The output for the get-status command looks like the following::

  2015-05-27T18:58:21Z    manifestVersion:2.0
  generator:Text editor
  bucket:myBucket
  deviceId:49382
  eraseDevice:yes
  notificationEmail:john.doe@example.com;jane.roe@example.com
  trueCryptPassword:password123
  acl:private
  serviceLevel:standard
  returnAddress:
      name: Jane Roe
      company: Example Corp.
      street1: 123 Any Street
      street2:
      street3:
      city: Anytown
      stateOrProvince: WA
      postalCode: 91011-1111
      country:USA
      phoneNumber:206-555-1111    0       EX1ID   Import  NotReceived     AWS has not received your device.       Pending The specified job has not started.
  ktKDXpdbEXAMPLEyGFJmQO744UHw=    version:2.0
  signingMethod:HmacSHA1
  jobId:EX1ID
  signature:ktKDXpdbEXAMPLEyGFJmQO744UHw=

When you ship your device, it will be delivered to a sorting facility, and then forwarded on to an AWS data center. Note that when you send a get-status command, the status of your job will not show as ``At AWS`` until the shipment has been received at the AWS data center.


======
Output
======

JobId -> (string)

  A unique identifier which refers to a particular job.

  

JobType -> (string)

  Specifies whether the job to initiate is an import or export job.

  

LocationCode -> (string)

  A token representing the location of the storage device, such as "AtAWS".

  

LocationMessage -> (string)

  A more human readable form of the physical location of the storage device.

  

ProgressCode -> (string)

  A token representing the state of the job, such as "Started".

  

ProgressMessage -> (string)

  A more human readable form of the job status.

  

Carrier -> (string)

  Name of the shipping company. This value is included when the LocationCode is "Returned".

  

TrackingNumber -> (string)

  The shipping tracking number assigned by AWS Import/Export to the storage device when it's returned to you. We return this value when the LocationCode is "Returned".

  

LogBucket -> (string)

  Amazon S3 bucket for user logs.

  

LogKey -> (string)

  The key where the user logs were stored.

  

ErrorCount -> (integer)

  Number of errors. We return this value when the ProgressCode is Success or SuccessWithErrors.

  

Signature -> (string)

  An encrypted code used to authenticate the request and response, for example, "DV+TpDfx1/TdSE9ktyK9k/bDTVI=". Only use this value is you want to create the signature file yourself. Generally you should use the SignatureFileContents value.

  

SignatureFileContents -> (string)

  An encrypted code used to authenticate the request and response, for example, "DV+TpDfx1/TdSE9ktyK9k/bDTVI=". Only use this value is you want to create the signature file yourself. Generally you should use the SignatureFileContents value.

  

CurrentManifest -> (string)

  The last manifest submitted, which will be used to process the job.

  

CreationDate -> (timestamp)

  Timestamp of the create-job request in ISO8601 date format. For example "2010-03-28T20:27:35Z".

  

ArtifactList -> (list)

  A collection of artifacts.

  (structure)

    A discrete item that contains the description and URL of an artifact (such as a PDF).

    Description -> (string)

      The associated description for this object.

      

    URL -> (string)

      The URL for a given Artifact.

      

    

  

