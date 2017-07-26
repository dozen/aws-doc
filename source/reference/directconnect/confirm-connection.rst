[ :ref:`aws <cli:aws>` . :ref:`directconnect <cli:aws directconnect>` ]

.. _cli:aws directconnect confirm-connection:


******************
confirm-connection
******************



===========
Description
===========



Confirm the creation of a hosted connection on an interconnect.

 

Upon creation, the hosted connection is initially in the 'Ordering' state, and will remain in this state until the owner calls confirm-connection to confirm creation of the hosted connection.



========
Synopsis
========

::

    confirm-connection
  --connection-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--connection-id`` (string)


  ID of the connection.

   

  Example: dxcon-fg5678gh

   

  Default: None

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

connectionState -> (string)

  State of the connection. 

   
  * **Ordering** : The initial state of a hosted connection provisioned on an interconnect. The connection stays in the ordering state until the owner of the hosted connection confirms or declines the connection order.
   
  * **Requested** : The initial state of a standard connection. The connection stays in the requested state until the Letter of Authorization (LOA) is sent to the customer.
   
  * **Pending** : The connection has been approved, and is being initialized.
   
  * **Available** : The network link is up, and the connection is ready for use.
   
  * **Down** : The network link is down.
   
  * **Deleting** : The connection is in the process of being deleted.
   
  * **Deleted** : The connection has been deleted.
   
  * **Rejected** : A hosted connection in the 'Ordering' state will enter the 'Rejected' state if it is deleted by the end customer.
   

  

  

