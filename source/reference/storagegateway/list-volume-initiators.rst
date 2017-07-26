[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway list-volume-initiators:


**********************
list-volume-initiators
**********************



===========
Description
===========



This operation lists iSCSI initiators that are connected to a volume. You can use this operation to determine whether a volume is being used or not.



========
Synopsis
========

::

    list-volume-initiators
  --volume-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--volume-arn`` (string)


  The Amazon Resource Name (ARN) of the volume. Use the  list-volumes operation to return a list of gateway volumes for the gateway.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Initiators -> (list)

  

  The host names and port numbers of all iSCSI initiators that are connected to the gateway.

  

  (string)

    

    

  

