[ :ref:`aws <cli:aws>` . :ref:`directconnect <cli:aws directconnect>` ]

.. _cli:aws directconnect confirm-private-virtual-interface:


*********************************
confirm-private-virtual-interface
*********************************



===========
Description
===========



Accept ownership of a private virtual interface created by another customer.

 

After the virtual interface owner calls this function, the virtual interface will be created and attached to the given virtual private gateway, and will be available for handling traffic.



========
Synopsis
========

::

    confirm-private-virtual-interface
  --virtual-interface-id <value>
  --virtual-gateway-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--virtual-interface-id`` (string)


  ID of the virtual interface.

   

  Example: dxvif-123dfg56

   

  Default: None

  

``--virtual-gateway-id`` (string)


  ID of the virtual private gateway that will be attached to the virtual interface.

   

  A virtual private gateway can be managed via the Amazon Virtual Private Cloud (VPC) console or the `EC2 CreateVpnGateway`_ action.

   

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
   

  

  



.. _EC2 CreateVpnGateway: http://docs.aws.amazon.com/AWSEC2/latest/APIReference/ApiReference-query-CreateVpnGateway.html