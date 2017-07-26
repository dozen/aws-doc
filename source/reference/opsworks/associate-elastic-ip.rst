[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks associate-elastic-ip:


********************
associate-elastic-ip
********************



===========
Description
===========



Associates one of the stack's registered Elastic IP addresses with a specified instance. The address must first be registered with the stack by calling  register-elastic-ip . For more information, see `Resource Management <http://docs.aws.amazon.com/opsworks/latest/userguide/resources.html>`_ .

 

 **Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/AssociateElasticIp>`_


========
Synopsis
========

::

    associate-elastic-ip
  --elastic-ip <value>
  [--instance-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--elastic-ip`` (string)


  The Elastic IP address.

  

``--instance-id`` (string)


  The instance ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To associate an Elastic IP address with an instance**

The following example associates an Elastic IP address with a specified instance. ::

  aws opsworks --region us-east-1 associate-elastic-ip --instance-id dfe18b02-5327-493d-91a4-c5c0c448927f --elastic-ip 54.148.130.96

*Output*: None.

**More Information**

For more information, see `Resource Management`_ in the *AWS OpsWorks User Guide*.

.. _`Resource Management`: http://docs.aws.amazon.com/opsworks/latest/userguide/resources.html



======
Output
======

None