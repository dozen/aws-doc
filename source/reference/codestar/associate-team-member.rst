[ :ref:`aws <cli:aws>` . :ref:`codestar <cli:aws codestar>` ]

.. _cli:aws codestar associate-team-member:


*********************
associate-team-member
*********************



===========
Description
===========



Adds an IAM user to the team for an AWS CodeStar project.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codestar-2017-04-19/AssociateTeamMember>`_


========
Synopsis
========

::

    associate-team-member
  --project-id <value>
  [--client-request-token <value>]
  --user-arn <value>
  --project-role <value>
  [--remote-access-allowed | --no-remote-access-allowed]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--project-id`` (string)


  The ID of the project to which you will add the IAM user.

  

``--client-request-token`` (string)


  A user- or system-generated token that identifies the entity that requested the team member association to the project. This token can be used to repeat the request. 

  

``--user-arn`` (string)


  The Amazon Resource Name (ARN) for the IAM user you want to add to the DevHub project.

  

``--project-role`` (string)


  The AWS CodeStar project role that will apply to this user. This role determines what actions a user can take in an AWS CodeStar project.

  

``--remote-access-allowed`` | ``--no-remote-access-allowed`` (boolean)


  Whether the team member is allowed to use an SSH public/private key pair to remotely access project resources, for example Amazon EC2 instances.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

clientRequestToken -> (string)

  

  The user- or system-generated token from the initial request that can be used to repeat the request. 

  

  

