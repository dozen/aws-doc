[ :ref:`aws <cli:aws>` . :ref:`codestar <cli:aws codestar>` ]

.. _cli:aws codestar update-team-member:


******************
update-team-member
******************



===========
Description
===========



Updates a team member's attributes in an AWS CodeStar project. For example, you can change a team member's role in the project, or change whether they have remote access to project resources.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codestar-2017-04-19/UpdateTeamMember>`_


========
Synopsis
========

::

    update-team-member
  --project-id <value>
  --user-arn <value>
  [--project-role <value>]
  [--remote-access-allowed | --no-remote-access-allowed]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--project-id`` (string)


  The ID of the project.

  

``--user-arn`` (string)


  The Amazon Resource Name (ARN) of the user for whom you want to change team membership attributes.

  

``--project-role`` (string)


  The role assigned to the user in the project. Project roles have different levels of access. For more information, see `Working with Teams <http://docs.aws.amazon.com/codestar/latest/userguide/working-with-teams.html>`_ in the AWS CodeStar User Guide.

  

``--remote-access-allowed`` | ``--no-remote-access-allowed`` (boolean)


  Whether a team member is allowed to remotely access project resources using the SSH public key associated with the user's profile. Even if this is set to True, the user must associate a public key with their profile before the user can access resources.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

userArn -> (string)

  

  The Amazon Resource Name (ARN) of the user whose team membership attributes were updated.

  

  

projectRole -> (string)

  

  The project role granted to the user.

  

  

remoteAccessAllowed -> (boolean)

  

  Whether a team member is allowed to remotely access project resources using the SSH public key associated with the user's profile.

  

  

