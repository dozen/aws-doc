[ :ref:`aws <cli:aws>` . :ref:`route53domains <cli:aws route53domains>` ]

.. _cli:aws route53domains get-operation-detail:


********************
get-operation-detail
********************



===========
Description
===========



This operation returns the current status of an operation that is not completed.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53domains-2014-05-15/GetOperationDetail>`_


========
Synopsis
========

::

    get-operation-detail
  --operation-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--operation-id`` (string)


  The identifier for the operation for which you want to get the status. Amazon Route 53 returned the identifier in the response to the original request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

OperationId -> (string)

  

  The identifier for the operation.

  

  

Status -> (string)

  

  The current status of the requested operation in the system.

  

  

Message -> (string)

  

  Detailed information on the status including possible errors.

  

  

DomainName -> (string)

  

  The name of a domain.

  

  

Type -> (string)

  

  The type of operation that was requested.

  

  

SubmittedDate -> (timestamp)

  

  The date when the request was submitted.

  

  

