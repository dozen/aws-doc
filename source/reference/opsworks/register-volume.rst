[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks register-volume:


***************
register-volume
***************



===========
Description
===========



Registers an Amazon EBS volume with a specified stack. A volume can be registered with only one stack at a time. If the volume is already registered, you must first deregister it by calling  deregister-volume . For more information, see `Resource Management <http://docs.aws.amazon.com/opsworks/latest/userguide/resources.html>`_ .

 

 **Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/RegisterVolume>`_


========
Synopsis
========

::

    register-volume
  [--ec-2-volume-id <value>]
  --stack-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--ec-2-volume-id`` (string)


  The Amazon EBS volume ID.

  

``--stack-id`` (string)


  The stack ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To register an Amazon EBS volume with a stack**

The following example registers an Amazon EBS volume, identified by its volume ID, with a specified stack. ::

  aws opsworks register-volume --region us-east-1 --stack-id d72553d4-8727-448c-9b00-f024f0ba1b06 --ec-2-volume-id vol-295c1638

*Output*::

  {
    "VolumeId": "ee08039c-7cb7-469f-be10-40fb7f0c05e8"
  }


**More Information**

For more information, see `Registering Amazon EBS Volumes with a Stack`_ in the *AWS OpsWorks User Guide*.

.. _`Registering Amazon EBS Volumes with a Stack`: http://docs.aws.amazon.com/opsworks/latest/userguide/resources-reg.html#resources-reg-ebs


======
Output
======

VolumeId -> (string)

  

  The volume ID.

  

  

