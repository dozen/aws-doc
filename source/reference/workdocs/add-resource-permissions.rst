[ :ref:`aws <cli:aws>` . :ref:`workdocs <cli:aws workdocs>` ]

.. _cli:aws workdocs add-resource-permissions:


************************
add-resource-permissions
************************



===========
Description
===========



Creates a set of permissions for the specified folder or document. The resource permissions are overwritten if the principals already have different permissions.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/workdocs-2016-05-01/AddResourcePermissions>`_


========
Synopsis
========

::

    add-resource-permissions
  [--authentication-token <value>]
  --resource-id <value>
  --principals <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--authentication-token`` (string)


  Amazon WorkDocs authentication token. This field should not be set when using administrative API actions, as in accessing the API using AWS credentials.

  

``--resource-id`` (string)


  The ID of the resource.

  

``--principals`` (list)


  The users, groups, or organization being granted permission.

  



Shorthand Syntax::

    Id=string,Type=string,Role=string ...




JSON Syntax::

  [
    {
      "Id": "string",
      "Type": "USER"|"GROUP"|"INVITE"|"ANONYMOUS"|"ORGANIZATION",
      "Role": "VIEWER"|"CONTRIBUTOR"|"OWNER"|"COOWNER"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ShareResults -> (list)

  

  The share results.

  

  (structure)

    

    Describes the share results of a resource.

    

    PrincipalId -> (string)

      

      The ID of the principal.

      

      

    Role -> (string)

      

      The role.

      

      

    Status -> (string)

      

      The status.

      

      

    ShareId -> (string)

      

      The ID of the resource that was shared.

      

      

    StatusMessage -> (string)

      

      The status message.

      

      

    

  

