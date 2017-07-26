[ :ref:`aws <cli:aws>` . :ref:`cloudhsm <cli:aws cloudhsm>` ]

.. _cli:aws cloudhsm list-luna-clients:


*****************
list-luna-clients
*****************



===========
Description
===========



Lists all of the clients.

 

This operation supports pagination with the use of the *NextToken* member. If more results are available, the *NextToken* member of the response contains a token that you pass in the next call to  list-luna-clients to retrieve the next set of items.



========
Synopsis
========

::

    list-luna-clients
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--next-token`` (string)


  The *NextToken* value from a previous call to  list-luna-clients . Pass null if this is the first call.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ClientList -> (list)

  

  The list of clients.

  

  (string)

    

    

  

NextToken -> (string)

  

  If not null, more results are available. Pass this to  list-luna-clients to retrieve the next set of items.

  

  

