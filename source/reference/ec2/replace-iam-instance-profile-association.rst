[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 replace-iam-instance-profile-association:


****************************************
replace-iam-instance-profile-association
****************************************



===========
Description
===========



Replaces an IAM instance profile for the specified running instance. You can use this action to change the IAM instance profile that's associated with an instance without having to disassociate the existing IAM instance profile first.

 

Use  describe-iam-instance-profile-associations to get the association ID.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/ReplaceIamInstanceProfileAssociation>`_


========
Synopsis
========

::

    replace-iam-instance-profile-association
  --iam-instance-profile <value>
  --association-id <value>
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



``--association-id`` (string)


  The ID of the existing IAM instance profile association.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

    

    

  

