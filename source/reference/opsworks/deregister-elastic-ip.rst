[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks deregister-elastic-ip:


*********************
deregister-elastic-ip
*********************



===========
Description
===========



Deregisters a specified Elastic IP address. The address can then be registered by another stack. For more information, see `Resource Management`_ .

 

**Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    deregister-elastic-ip
  --elastic-ip <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--elastic-ip`` (string)


  The Elastic IP address.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To deregister an Elastic IP address from a stack**

The following example deregisters an Elastic IP address, identified by its IP address, from its stack. ::

  aws opsworks deregister-elastic-ip --region us-east-1 --elastic-ip 54.148.130.96 

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

*Output*: None.

**More Information**

For more information, see `Deregistering Elastic IP Addresses`_ in the *AWS OpsWorks User Guide*.

.. _`Deregistering Elastic IP Addresses`: http://docs.aws.amazon.com/opsworks/latest/userguide/resources-dereg.html#resources-dereg-eip


======
Output
======

None

.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
.. _Resource Management: http://docs.aws.amazon.com/opsworks/latest/userguide/resources.html
