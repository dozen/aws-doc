[ :ref:`aws <cli:aws>` . :ref:`workspaces <cli:aws workspaces>` ]

.. _cli:aws workspaces describe-workspaces-connection-status:


*************************************
describe-workspaces-connection-status
*************************************



===========
Description
===========



Describes the connection status of a specified WorkSpace.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/workspaces-2015-04-08/DescribeWorkspacesConnectionStatus>`_


========
Synopsis
========

::

    describe-workspaces-connection-status
  [--workspace-ids <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--workspace-ids`` (list)


  An array of strings that contain the identifiers of the WorkSpaces.

  



Syntax::

  "string" "string" ...



``--next-token`` (string)


  The next token of the request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

WorkspacesConnectionStatus -> (list)

  

  The connection status of the WorkSpace.

  

  (structure)

    

    Describes the connection status of a WorkSpace.

    

    WorkspaceId -> (string)

      

      The ID of the WorkSpace.

      

      

    ConnectionState -> (string)

      

      The connection state of the WorkSpace. Returns UNKOWN if the WorkSpace is in a Stopped state.

      

      

    ConnectionStateCheckTimestamp -> (timestamp)

      

      The timestamp of the connection state check.

      

      

    LastKnownUserConnectionTimestamp -> (timestamp)

      

      The timestamp of the last known user connection.

      

      

    

  

NextToken -> (string)

  

  The next token of the result.

  

  

