[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks disassociate-elastic-ip:


***********************
disassociate-elastic-ip
***********************



===========
Description
===========



Disassociates an Elastic IP address from its instance. The address remains registered with the stack. For more information, see `Resource Management`_ .

 

**Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    disassociate-elastic-ip
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

**To disassociate an Elastic IP address from an instance**

The following example disassociates an Elastic IP address from a specified instance. ::

  aws opsworks --region us-east-1 disassociate-elastic-ip --elastic-ip 54.148.130.96

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

*Output*: None.

**More Information**

For more information, see `Resource Management`_ in the *AWS OpsWorks User Guide*.

.. _`Resource Management`: http://docs.aws.amazon.com/opsworks/latest/userguide/resources.html



======
Output
======

None

.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
.. _Resource Management: http://docs.aws.amazon.com/opsworks/latest/userguide/resources.html
