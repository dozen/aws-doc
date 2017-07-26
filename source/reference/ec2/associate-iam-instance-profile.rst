[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 associate-iam-instance-profile:


******************************
associate-iam-instance-profile
******************************



===========
Description
===========



Associates an IAM instance profile with a running or stopped instance. You cannot associate more than one IAM instance profile with an instance.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/AssociateIamInstanceProfile>`_


========
Synopsis
========

::

    associate-iam-instance-profile
  --iam-instance-profile <value>
  --instance-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--iam-instance-profile`` (structure)


  The IAM instance profile.

  



Shorthand Syntax::

    Arn=string,Name=string




JSON Syntax::

  {
    "Arn": "string",
    "Name": "string"
  }



``--instance-id`` (string)


  The ID of the instance.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To associate an IAM instance profile with an instance**

This example associates an IAM instance profile named ``admin-role`` with instance ``i-123456789abcde123``.

Command::

  aws ec2 associate-iam-instance-profile --instance-id i-123456789abcde123 --iam-instance-profile Name=admin-role

Output::

  {
    "IamInstanceProfileAssociation": {
        "InstanceId": "i-123456789abcde123",
        "State": "associating",
        "AssociationId": "iip-assoc-0e7736511a163c209",
        "IamInstanceProfile": {
            "Id": "AIPAJBLK7RKJKWDXVHIEC",
            "Arn": "arn:aws:iam::123456789012:instance-profile/admin-role"
        }
    }
  }


======
Output
======

IamInstanceProfileAssociation -> (structure)

  

  Information about the IAM instance profile association.

  

  AssociationId -> (string)

    

    The ID of the association.

    

    

  InstanceId -> (string)

    

    The ID of the instance.

    

    

  IamInstanceProfile -> (structure)

    

    The IAM instance profile.

    

    Arn -> (string)

      

      The Amazon Resource Name (ARN) of the instance profile.

      

      

    Id -> (string)

      

      The ID of the instance profile.

      

      

    

  State -> (string)

    

    The state of the association.

    

    

  Timestamp -> (timestamp)

    

    The time the IAM instance profile was associated with the instance.

    

    

  

