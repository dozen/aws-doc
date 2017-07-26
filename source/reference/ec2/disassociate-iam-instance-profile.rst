[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 disassociate-iam-instance-profile:


*********************************
disassociate-iam-instance-profile
*********************************



===========
Description
===========



Disassociates an IAM instance profile from a running or stopped instance.

 

Use  describe-iam-instance-profile-associations to get the association ID.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DisassociateIamInstanceProfile>`_


========
Synopsis
========

::

    disassociate-iam-instance-profile
  --association-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--association-id`` (string)


  The ID of the IAM instance profile association.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To disassociate an IAM instance profile**

This example disassociates an IAM instance profile with the association ID ``iip-assoc-05020b59952902f5f``.

Command::

  aws ec2 disassociate-iam-instance-profile --association-id iip-assoc-05020b59952902f5f

Output::

  {
    "IamInstanceProfileAssociation": {
        "InstanceId": "i-123456789abcde123",
        "State": "disassociating",
        "AssociationId": "iip-assoc-05020b59952902f5f",
        "IamInstanceProfile": {
            "Id": "AIPAI5IVIHMFFYY2DKV5Y",
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

    

    

  

