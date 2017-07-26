[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice delete-delivery-channel:


***********************
delete-delivery-channel
***********************



===========
Description
===========



Deletes the specified delivery channel.

 

The delivery channel cannot be deleted if it is the only delivery channel and the configuration recorder is still running. To delete the delivery channel, stop the running configuration recorder using the  stop-configuration-recorder action.



========
Synopsis
========

::

    delete-delivery-channel
  --delivery-channel-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--delivery-channel-name`` (string)


  The name of the delivery channel to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a delivery channel**

The following command deletes the default delivery channel::

    aws configservice delete-delivery-channel --delivery-channel-name default

======
Output
======

None