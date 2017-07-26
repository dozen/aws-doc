[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway delete-tape:


***********
delete-tape
***********



===========
Description
===========



Deletes the specified virtual tape.



========
Synopsis
========

::

    delete-tape
  --gateway-arn <value>
  --tape-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--gateway-arn`` (string)


  The unique Amazon Resource Name (ARN) of the gateway that the virtual tape to delete is associated with. Use the  list-gateways operation to return a list of gateways for your account and region.

  

``--tape-arn`` (string)


  The Amazon Resource Name (ARN) of the virtual tape to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

TapeARN -> (string)

  

  The Amazon Resource Name (ARN) of the deleted virtual tape.

  

  

