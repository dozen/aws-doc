[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-iam-instance-profile-associations:


******************************************
describe-iam-instance-profile-associations
******************************************



===========
Description
===========



Describes your IAM instance profile associations.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeIamInstanceProfileAssociations>`_


========
Synopsis
========

::

    describe-iam-instance-profile-associations
  [--association-ids <value>]
  [--filters <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--association-ids`` (list)


  One or more IAM instance profile associations.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters.

   

   
  * ``instance-id`` - The ID of the instance. 
   
  * ``state`` - The state of the association (``associating`` | ``associated`` | ``disassociating`` | ``disassociated`` ). 
   

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--max-results`` (integer)


  The maximum number of results to return in a single call. To retrieve the remaining results, make another call with the returned ``next-token`` value.

  

``--next-token`` (string)


  The token to request the next page of results.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe IAM instance profile associations**

This example describes all of your IAM instance profile associations.

Command::

  aws ec2 describe-iam-instance-profile-associations

Output::

  {
    "IamInstanceProfileAssociations": [
        {
            "InstanceId": "i-09eb09efa73ec1dee",
            "State": "associated",
            "AssociationId": "iip-assoc-0db249b1f25fa24b8",
            "IamInstanceProfile": {
                "Id": "AIPAJVQN4F5WVLGCJDRGM",
                "Arn": "arn:aws:iam::123456789012:instance-profile/admin-role"
            }
        },
        {
            "InstanceId": "i-0402909a2f4dffd14",
            "State": "associating",
            "AssociationId": "iip-assoc-0d1ec06278d29f44a",
            "IamInstanceProfile": {
                "Id": "AGJAJVQN4F5WVLGCJABCM",
                "Arn": "arn:aws:iam::123456789012:instance-profile/user1-role"
            }
        }
     ]
  }


======
Output
======

IamInstanceProfileAssociations -> (list)

  

  Information about one or more IAM instance profile associations.

  

  (structure)

    

    Describes an association between an IAM instance profile and an instance.

    

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

      

      

    

  

NextToken -> (string)

  

  The token to use to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

