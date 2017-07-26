[ :ref:`aws <cli:aws>` . :ref:`opsworkscm <cli:aws opsworkscm>` ]

.. _cli:aws opsworkscm disassociate-node:


*****************
disassociate-node
*****************



===========
Description
===========



Disassociates a node from a Chef server, and removes the node from the Chef server's managed nodes. After a node is disassociated, the node key pair is no longer valid for accessing the Chef API. For more information about how to associate a node, see  associate-node . 

 

A node can can only be disassociated from a server that is in a ``HEALTHY`` state. Otherwise, an ``InvalidStateException`` is thrown. A ``ResourceNotFoundException`` is thrown when the server does not exist. A ``ValidationException`` is raised when parameters of the request are not valid. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworkscm-2016-11-01/DisassociateNode>`_


========
Synopsis
========

::

    disassociate-node
  --server-name <value>
  --node-name <value>
  [--engine-attributes <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--server-name`` (string)


  The name of the server from which to disassociate the node. 

  

``--node-name`` (string)


  The name of the Chef client node. 

  

``--engine-attributes`` (list)


  Engine attributes used for disassociating the node. 

   

   **Attributes accepted in a disassociate-node request:**  

   

   
  * ``CHEF_ORGANIZATION`` : The Chef organization with which the node was associated. By default only one organization named ``default`` can exist.  
   

  



Shorthand Syntax::

    Name=string,Value=string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Value": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To disassociate nodes**

The following ``disassociate-node`` command disassociates a node named ``i-44de882p``, removing the node from
management by a Chef Automate server named ``automate-06``. Valid node names are EC2 instance IDs.::

  aws opsworks-cm disassociate-node --server-name "automate-06" --node-name "i-43de882p" --engine-attributes "Name=CHEF_ORGANIZATION,Value='default'"

The output returned by the command resembles the following.
*Output*::

  {
   "NodeAssociationStatusToken": "AHUY8wFe4pdXtZC5DiJa5SOLp5o14DH//rHRqHDWXxwVoNBxcEy4V7R0NOFymh7E/1HumOBPsemPQFE6dcGaiFk"
  }

**More Information**

For more information, see `Delete an AWS OpsWorks for Chef Automate Server`_ in the *AWS OpsWorks User Guide*.

.. _`Delete an AWS OpsWorks for Chef Automate Server`: http://docs.aws.amazon.com/opsworks/latest/userguide/opscm-delete-server.html


======
Output
======

NodeAssociationStatusToken -> (string)

  

  Contains a token which can be passed to the ``describe-node-association-status`` API call to get the status of the disassociation request. 

  

  

