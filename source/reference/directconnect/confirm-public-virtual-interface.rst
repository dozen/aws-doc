[ :ref:`aws <cli:aws>` . :ref:`directconnect <cli:aws directconnect>` ]

.. _cli:aws directconnect confirm-public-virtual-interface:


********************************
confirm-public-virtual-interface
********************************



===========
Description
===========



Accept ownership of a public virtual interface created by another customer.

 

After the virtual interface owner calls this function, the specified virtual interface will be created and made available for handling traffic.



========
Synopsis
========

::

    confirm-public-virtual-interface
  --virtual-interface-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--virtual-interface-id`` (string)


  ID of the virtual interface.

   

  Example: dxvif-123dfg56

   

  Default: None

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

virtualInterfaceState -> (string)

  State of the virtual interface. 

   
  * **Confirming** : The creation of the virtual interface is pending confirmation from the virtual interface owner. If the owner of the virtual interface is different from the owner of the connection on which it is provisioned, then the virtual interface will remain in this state until it is confirmed by the virtual interface owner.
   
  * **Verifying** : This state only applies to public virtual interfaces. Each public virtual interface needs validation before the virtual interface can be created.
   
  * **Pending** : A virtual interface is in this state from the time that it is created until the virtual interface is ready to forward traffic.
   
  * **Available** : A virtual interface that is able to forward traffic.
   
  * **Down** : A virtual interface that is BGP down.
   
  * **Deleting** : A virtual interface is in this state immediately after calling *delete-virtual-interface* until it can no longer forward traffic.
   
  * **Deleted** : A virtual interface that cannot forward traffic.
   
  * **Rejected** : The virtual interface owner has declined creation of the virtual interface. If a virtual interface in the 'Confirming' state is deleted by the virtual interface owner, the virtual interface will enter the 'Rejected' state.
   

  

  

