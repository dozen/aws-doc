[ :ref:`aws <cli:aws>` . :ref:`codestar <cli:aws codestar>` ]

.. _cli:aws codestar list-user-profiles:


******************
list-user-profiles
******************



===========
Description
===========



Lists all the user profiles configured for your AWS account in AWS CodeStar.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codestar-2017-04-19/ListUserProfiles>`_


========
Synopsis
========

::

    list-user-profiles
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--next-token`` (string)


  The continuation token for the next set of results, if the results cannot be returned in one response.

  

``--max-results`` (integer)


  The maximum number of results to return in a response.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

userProfiles -> (list)

  

  All the user profiles configured in AWS CodeStar for an AWS account.

  

  (structure)

    

    Information about a user's profile in AWS CodeStar.

    

    userArn -> (string)

      

      The Amazon Resource Name (ARN) of the user in IAM.

      

      

    displayName -> (string)

      

      The display name of a user in AWS CodeStar. For example, this could be set to both first and last name ("Mary Major") or a single name ("Mary"). The display name is also used to generate the initial icon associated with the user in AWS CodeStar projects. If spaces are included in the display name, the first character that appears after the space will be used as the second character in the user initial icon. The initial icon displays a maximum of two characters, so a display name with more than one space (for example "Mary Jane Major") would generate an initial icon using the first character and the first character after the space ("MJ", not "MM").

      

      

    emailAddress -> (string)

      

      The email address associated with the user.

      

      

    sshPublicKey -> (string)

      

      The SSH public key associated with the user in AWS CodeStar. If a project owner allows the user remote access to project resources, this public key will be used along with the user's private key for SSH access.

      

      

    

  

nextToken -> (string)

  

  The continuation token to use when requesting the next set of results, if there are more results to be returned.

  

  

