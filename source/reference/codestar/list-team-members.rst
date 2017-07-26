[ :ref:`aws <cli:aws>` . :ref:`codestar <cli:aws codestar>` ]

.. _cli:aws codestar list-team-members:


*****************
list-team-members
*****************



===========
Description
===========



Lists all team members associated with a project.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codestar-2017-04-19/ListTeamMembers>`_


========
Synopsis
========

::

    list-team-members
  --project-id <value>
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--project-id`` (string)


  The ID of the project for which you want to list team members.

  

``--next-token`` (string)


  The continuation token for the next set of results, if the results cannot be returned in one response.

  

``--max-results`` (integer)


  The maximum number of team members you want returned in a response.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

teamMembers -> (list)

  

  A list of team member objects for the project.

  

  (structure)

    

    Information about a team member in a project.

    

    userArn -> (string)

      

      The Amazon Resource Name (ARN) of the user in IAM.

      

      

    projectRole -> (string)

      

      The role assigned to the user in the project. Project roles have different levels of access. For more information, see `Working with Teams <http://docs.aws.amazon.com/codestar/latest/userguide/working-with-teams.html>`_ in the AWS CodeStar User Guide. 

      

      

    remoteAccessAllowed -> (boolean)

      

      Whether the user is allowed to remotely access project resources using an SSH public/private key pair.

      

      

    

  

nextToken -> (string)

  

  The continuation token to use when requesting the next set of results, if there are more results to be returned.

  

  

