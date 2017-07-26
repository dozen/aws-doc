[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks register-elastic-ip:


*******************
register-elastic-ip
*******************



===========
Description
===========



Registers an Elastic IP address with a specified stack. An address can be registered with only one stack at a time. If the address is already registered, you must first deregister it by calling  deregister-elastic-ip . For more information, see `Resource Management <http://docs.aws.amazon.com/opsworks/latest/userguide/resources.html>`_ .

 

 **Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/RegisterElasticIp>`_


========
Synopsis
========

::

    register-elastic-ip
  --elastic-ip <value>
  --stack-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--elastic-ip`` (string)


  The Elastic IP address.

  

``--stack-id`` (string)


  The stack ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To register an Elastic IP address with a stack**

The following example registers an Elastic IP address, identified by its IP address, with a specified stack.

**Note:** The Elastic IP address must be in the same region as the stack. ::

  aws opsworks register-elastic-ip --region us-east-1 --stack-id d72553d4-8727-448c-9b00-f024f0ba1b06 --elastic-ip 54.148.130.96 

*Output* ::

  {
    "ElasticIp": "54.148.130.96"
  }

**More Information**

For more information, see `Registering Elastic IP Addresses with a Stack`_ in the *OpsWorks User Guide*.

.. _`Registering Elastic IP Addresses with a Stack`: http://docs.aws.amazon.com/opsworks/latest/userguide/resources-reg.html#resources-reg-eip


======
Output
======

ElasticIp -> (string)

  

  The Elastic IP address.

  

  

