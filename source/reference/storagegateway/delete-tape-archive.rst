[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway delete-tape-archive:


*******************
delete-tape-archive
*******************



===========
Description
===========



Deletes the specified virtual tape from the virtual tape shelf (VTS).



========
Synopsis
========

::

    delete-tape-archive
  --tape-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--tape-arn`` (string)


  The Amazon Resource Name (ARN) of the virtual tape to delete from the virtual tape shelf (VTS).

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

TapeARN -> (string)

  

  The Amazon Resource Name (ARN) of the virtual tape that was deleted from the virtual tape shelf (VTS).

  

  

