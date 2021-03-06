[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier list-provisioned-capacity:


*************************
list-provisioned-capacity
*************************



===========
Description
===========



This operation lists the provisioned capacity for the specified AWS account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/glacier-2012-06-01/ListProvisionedCapacity>`_


========
Synopsis
========

::

    list-provisioned-capacity
  --account-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--account-id`` (string)


  The ``AccountId`` value is the AWS account ID of the account that owns the vault. You can either specify an AWS account ID or optionally a single '-' (hyphen), in which case Amazon Glacier uses the AWS account ID associated with the credentials used to sign the request. If you use an account ID, don't include any hyphens ('-') in the ID. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON account-id provided. The JSON account-id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ProvisionedCapacityList -> (list)

  

  The response body contains the following JSON fields.

  

  (structure)

    

    The definition for a provisioned capacity unit.

    

    CapacityId -> (string)

      

      The ID that identifies the provisioned capacity unit.

      

      

    StartDate -> (string)

      

      The date that the provisioned capacity unit was purchased, in Universal Coordinated Time (UTC).

      

      

    ExpirationDate -> (string)

      

      The date that the provisioned capacity unit expires, in Universal Coordinated Time (UTC).

      

      

    

  

