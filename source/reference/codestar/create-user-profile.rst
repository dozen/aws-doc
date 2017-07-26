[ :ref:`aws <cli:aws>` . :ref:`codestar <cli:aws codestar>` ]

.. _cli:aws codestar create-user-profile:


*******************
create-user-profile
*******************



===========
Description
===========



Creates a profile for a user that includes user preferences, such as the display name and email address assocciated with the user, in AWS CodeStar. The user profile is not project-specific. Information in the user profile is displayed wherever the user's information appears to other users in AWS CodeStar.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codestar-2017-04-19/CreateUserProfile>`_


========
Synopsis
========

::

    create-user-profile
  --user-arn <value>
  --display-name <value>
  --email-address <value>
  [--ssh-public-key <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-arn`` (string)


  The Amazon Resource Name (ARN) of the user in IAM.

  

``--display-name`` (string)


  The name that will be displayed as the friendly name for the user in AWS CodeStar. 

  

``--email-address`` (string)


  The email address that will be displayed as part of the user's profile in AWS CodeStar.

  

``--ssh-public-key`` (string)


  The SSH public key associated with the user in AWS CodeStar. If a project owner allows the user remote access to project resources, this public key will be used along with the user's private key for SSH access.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

userArn -> (string)

  

  The Amazon Resource Name (ARN) of the user in IAM.

  

  

displayName -> (string)

  

  The name that is displayed as the friendly name for the user in AWS CodeStar.

  

  

emailAddress -> (string)

  

  The email address that is displayed as part of the user's profile in AWS CodeStar.

  

  

sshPublicKey -> (string)

  

  The SSH public key associated with the user in AWS CodeStar. This is the public portion of the public/private keypair the user can use to access project resources if a project owner allows the user remote access to those resources.

  

  

createdTimestamp -> (timestamp)

  

  The date the user profile was created, in timestamp format.

  

  

lastModifiedTimestamp -> (timestamp)

  

  The date the user profile was last modified, in timestamp format.

  

  

