[ :ref:`aws <cli:aws>` . :ref:`cloudhsm <cli:aws cloudhsm>` ]

.. _cli:aws cloudhsm list-hsms:


*********
list-hsms
*********



===========
Description
===========



Retrieves the identifiers of all of the HSMs provisioned for the current customer.

 

This operation supports pagination with the use of the *NextToken* member. If more results are available, the *NextToken* member of the response contains a token that you pass in the next call to  list-hsms to retrieve the next set of items.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudhsm-2014-05-30/ListHsms>`_


========
Synopsis
========

::

    list-hsms
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--next-token`` (string)


  The *NextToken* value from a previous call to  list-hsms . Pass null if this is the first call.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

HsmList -> (list)

  

  The list of ARNs that identify the HSMs.

  

  (string)

    

    An ARN that identifies an HSM.

    

    

  

NextToken -> (string)

  

  If not null, more results are available. Pass this value to  list-hsms to retrieve the next set of items.

  

  

