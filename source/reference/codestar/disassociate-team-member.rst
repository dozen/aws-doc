[ :ref:`aws <cli:aws>` . :ref:`codestar <cli:aws codestar>` ]

.. _cli:aws codestar disassociate-team-member:


************************
disassociate-team-member
************************



===========
Description
===========



Removes a user from a project. Removing a user from a project also removes the IAM policies from that user that allowed access to the project and its resources. Disassociating a team member does not remove that user's profile from AWS CodeStar. It does not remove the user from IAM.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codestar-2017-04-19/DisassociateTeamMember>`_


========
Synopsis
========

::

    disassociate-team-member
  --project-id <value>
  --user-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--project-id`` (string)


  The ID of the AWS CodeStar project from which you want to remove a team member.

  

``--user-arn`` (string)


  The Amazon Resource Name (ARN) of the IAM user or group whom you want to remove from the project.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

