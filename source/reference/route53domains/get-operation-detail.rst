[ :ref:`aws <cli:aws>` . :ref:`route53domains <cli:aws route53domains>` ]

.. _cli:aws route53domains get-operation-detail:


********************
get-operation-detail
********************



===========
Description
===========



This operation returns the current status of an operation that is not completed.



========
Synopsis
========

::

    get-operation-detail
  --operation-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--operation-id`` (string)


  The identifier for the operation for which you want to get the status. Amazon Route 53 returned the identifier in the response to the original request.

   

  Type: String

   

  Default: None

   

  Required: Yes

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

OperationId -> (string)

  

  The identifier for the operation.

   

  Type: String

  

  

Status -> (string)

  

  The current status of the requested operation in the system.

   

  Type: String

  

  

Message -> (string)

  

  Detailed information on the status including possible errors.

   

  Type: String

  

  

DomainName -> (string)

  

  The name of a domain.

   

  Type: String

  

  

Type -> (string)

  

  The type of operation that was requested.

   

  Type: String

  

  

SubmittedDate -> (timestamp)

  

  The date when the request was submitted.

  

  

