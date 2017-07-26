[ :ref:`aws <cli:aws>` . :ref:`cloudhsm <cli:aws cloudhsm>` ]

.. _cli:aws cloudhsm list-hapgs:


**********
list-hapgs
**********



===========
Description
===========



Lists the high-availability partition groups for the account.

 

This operation supports pagination with the use of the *NextToken* member. If more results are available, the *NextToken* member of the response contains a token that you pass in the next call to  list-hapgs to retrieve the next set of items.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudhsm-2014-05-30/ListHapgs>`_


========
Synopsis
========

::

    list-hapgs
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--next-token`` (string)


  The *NextToken* value from a previous call to  list-hapgs . Pass null if this is the first call.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

HapgList -> (list)

  

  The list of high-availability partition groups.

  

  (string)

    

    

  

NextToken -> (string)

  

  If not null, more results are available. Pass this value to  list-hapgs to retrieve the next set of items.

  

  

