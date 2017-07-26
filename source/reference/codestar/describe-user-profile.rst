[ :ref:`aws <cli:aws>` . :ref:`codestar <cli:aws codestar>` ]

.. _cli:aws codestar describe-user-profile:


*********************
describe-user-profile
*********************



===========
Description
===========



Describes a user in AWS CodeStar and the user attributes across all projects.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codestar-2017-04-19/DescribeUserProfile>`_


========
Synopsis
========

::

    describe-user-profile
  --user-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-arn`` (string)


  The Amazon Resource Name (ARN) of the user.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

userArn -> (string)

  

  The Amazon Resource Name (ARN) of the user.

  

  

displayName -> (string)

  

  The display name shown for the user in AWS CodeStar projects. For example, this could be set to both first and last name ("Mary Major") or a single name ("Mary"). The display name is also used to generate the initial icon associated with the user in AWS CodeStar projects. If spaces are included in the display name, the first character that appears after the space will be used as the second character in the user initial icon. The initial icon displays a maximum of two characters, so a display name with more than one space (for example "Mary Jane Major") would generate an initial icon using the first character and the first character after the space ("MJ", not "MM").

  

  

emailAddress -> (string)

  

  The email address for the user. Optional.

  

  

sshPublicKey -> (string)

  

  The SSH public key associated with the user. This SSH public key is associated with the user profile, and can be used in conjunction with the associated private key for access to project resources, such as Amazon EC2 instances, if a project owner grants remote access to those resources.

  

  

createdTimestamp -> (timestamp)

  

  The date and time when the user profile was created in AWS CodeStar, in timestamp format.

  

  

lastModifiedTimestamp -> (timestamp)

  

  The date and time when the user profile was last modified, in timestamp format.

  

  

