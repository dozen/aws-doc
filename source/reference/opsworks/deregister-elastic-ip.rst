[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks deregister-elastic-ip:


*********************
deregister-elastic-ip
*********************



===========
Description
===========



Deregisters a specified Elastic IP address. The address can then be registered by another stack. For more information, see `Resource Management <http://docs.aws.amazon.com/opsworks/latest/userguide/resources.html>`_ .

 

 **Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/DeregisterElasticIp>`_


========
Synopsis
========

::

    deregister-elastic-ip
  --elastic-ip <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--elastic-ip`` (string)


  The Elastic IP address.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To deregister an Elastic IP address from a stack**

The following example deregisters an Elastic IP address, identified by its IP address, from its stack. ::

  aws opsworks deregister-elastic-ip --region us-east-1 --elastic-ip 54.148.130.96 

*Output*: None.

**More Information**

For more information, see `Deregistering Elastic IP Addresses`_ in the *AWS OpsWorks User Guide*.

.. _`Deregistering Elastic IP Addresses`: http://docs.aws.amazon.com/opsworks/latest/userguide/resources-dereg.html#resources-dereg-eip


======
Output
======

None