[ :ref:`aws <cli:aws>` . :ref:`opsworkscm <cli:aws opsworkscm>` ]

.. _cli:aws opsworkscm associate-node:


**************
associate-node
**************



===========
Description
===========



Associates a new node with the Chef server. This command is an alternative to ``knife bootstrap`` . For more information about how to disassociate a node, see  disassociate-node .

 

A node can can only be associated with servers that are in a ``HEALTHY`` state. Otherwise, an ``InvalidStateException`` is thrown. A ``ResourceNotFoundException`` is thrown when the server does not exist. A ``ValidationException`` is raised when parameters of the request are not valid. The associate-node API call can be integrated into Auto Scaling configurations, AWS Cloudformation templates, or the user data of a server's instance. 

 

Example: ``aws opsworks-cm associate-node --server-name *MyServer* --node-name *MyManagedNode* --engine-attributes "Name=*MyOrganization* ,Value=default" "Name=*Chef_node_public_key* ,Value=*Public_key_contents* "``  



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworkscm-2016-11-01/AssociateNode>`_


========
Synopsis
========

::

    associate-node
  --server-name <value>
  --node-name <value>
  --engine-attributes <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--server-name`` (string)


  The name of the server with which to associate the node. 

  

``--node-name`` (string)


  The name of the Chef client node. 

  

``--engine-attributes`` (list)


  Engine attributes used for associating the node. 

   

   **Attributes accepted in a associate-node request:**  

   

   
  * ``CHEF_ORGANIZATION`` : The Chef organization with which the node is associated. By default only one organization named ``default`` can exist.  
   
  * ``CHEF_NODE_PUBLIC_KEY`` : A PEM-formatted public key. This key is required for the ``chef-client`` agent to access the Chef API.  
   

  



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

**To associate nodes**

The following ``associate-node`` command associates a node named ``i-44de882p`` with
a Chef Automate server named ``automate-06``, meaning that the ``automate-06`` server
manages the node, and communicates recipe commands to the node through ``chef-client`` agent software
that is installed on the node by the associate-node command. Valid node names are EC2 instance IDs.::

  aws opsworks-cm disassociate-node --server-name "automate-06" --node-name "i-43de882p" --engine-attributes "Name=CHEF_ORGANIZATION,Value='default'"

The output returned by the command resembles the following.
*Output*::

  {
   "NodeAssociationStatusToken": "AHUY8wFe4pdXtZC5DiJa5SOLp5o14DH//rHRqHDWXxwVoNBxcEy4V7R0NOFymh7E/1HumOBPsemPQFE6dcGaiFk"
  }

**More Information**

For more information, see `Adding Nodes Automatically in AWS OpsWorks for Chef Automate`_ in the *AWS OpsWorks User Guide*.

.. _`Adding Nodes Automatically in AWS OpsWorks for Chef Automate`: http://docs.aws.amazon.com/opsworks/latest/userguide/opscm-unattend-assoc.html



======
Output
======

NodeAssociationStatusToken -> (string)

  

  Contains a token which can be passed to the ``describe-node-association-status`` API call to get the status of the association request. 

  

  

