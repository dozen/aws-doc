[ :ref:`aws <cli:aws>` . :ref:`directconnect <cli:aws directconnect>` ]

.. _cli:aws directconnect delete-interconnect:


*******************
delete-interconnect
*******************



===========
Description
===========



Deletes the specified interconnect.



========
Synopsis
========

::

    delete-interconnect
  --interconnect-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--interconnect-id`` (string)


  The ID of the interconnect.

   

  Example: dxcon-abc123

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

interconnectState -> (string)

  State of the interconnect. 

   
  * **Requested** : The initial state of an interconnect. The interconnect stays in the requested state until the Letter of Authorization (LOA) is sent to the customer.
   
  * **Pending** : The interconnect has been approved, and is being initialized.
   
  * **Available** : The network link is up, and the interconnect is ready for use.
   
  * **Down** : The network link is down.
   
  * **Deleting** : The interconnect is in the process of being deleted.
   
  * **Deleted** : The interconnect has been deleted.
   

  

  

