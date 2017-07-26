[ :ref:`aws <cli:aws>` . :ref:`directconnect <cli:aws directconnect>` ]

.. _cli:aws directconnect delete-interconnect:


*******************
delete-interconnect
*******************



===========
Description
===========



Deletes the specified interconnect.

 

.. note::

   

  This is intended for use by AWS Direct Connect partners only.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/directconnect-2012-10-25/DeleteInterconnect>`_


========
Synopsis
========

::

    delete-interconnect
  --interconnect-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--interconnect-id`` (string)


  The ID of the interconnect.

   

  Example: dxcon-abc123

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete an interconnect**

The following ``delete-interconnect`` command deletes the specified interconnect::

  aws directconnect delete-interconnect --interconnect-id dxcon-fgktov66

Output::

  {
      "interconnectState": "deleted"
  }

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
   

  

  

