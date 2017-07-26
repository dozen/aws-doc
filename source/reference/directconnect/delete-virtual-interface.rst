[ :ref:`aws <cli:aws>` . :ref:`directconnect <cli:aws directconnect>` ]

.. _cli:aws directconnect delete-virtual-interface:


************************
delete-virtual-interface
************************



===========
Description
===========



Deletes a virtual interface.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/directconnect-2012-10-25/DeleteVirtualInterface>`_


========
Synopsis
========

::

    delete-virtual-interface
  --virtual-interface-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--virtual-interface-id`` (string)


  The ID of the virtual interface.

   

  Example: dxvif-123dfg56

   

  Default: None

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a virtual interface**

The following ``delete-virtual-interface`` command deletes the specified virtual interface::

  aws directconnect delete-virtual-interface --virtual-interface-id dxvif-ffhhk74f

Output::

  {
      "virtualInterfaceState": "deleting"
  }

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
   
  * **Deleting** : A virtual interface is in this state immediately after calling  delete-virtual-interface until it can no longer forward traffic. 
   
  * **Deleted** : A virtual interface that cannot forward traffic. 
   
  * **Rejected** : The virtual interface owner has declined creation of the virtual interface. If a virtual interface in the 'Confirming' state is deleted by the virtual interface owner, the virtual interface will enter the 'Rejected' state. 
   

  

  

