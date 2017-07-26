[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds update-radius:


*************
update-radius
*************



===========
Description
===========



Updates the Remote Authentication Dial In User Service (RADIUS) server information for an AD Connector directory.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ds-2015-04-16/UpdateRadius>`_


========
Synopsis
========

::

    update-radius
  --directory-id <value>
  --radius-settings <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-id`` (string)


  The identifier of the directory for which to update the RADIUS server information.

  

``--radius-settings`` (structure)


  A  radius-settings object that contains information about the RADIUS server.

  



Shorthand Syntax::

    RadiusServers=string,string,RadiusPort=integer,RadiusTimeout=integer,RadiusRetries=integer,SharedSecret=string,AuthenticationProtocol=string,DisplayLabel=string,UseSameUsername=boolean




JSON Syntax::

  {
    "RadiusServers": ["string", ...],
    "RadiusPort": integer,
    "RadiusTimeout": integer,
    "RadiusRetries": integer,
    "SharedSecret": "string",
    "AuthenticationProtocol": "PAP"|"CHAP"|"MS-CHAPv1"|"MS-CHAPv2",
    "DisplayLabel": "string",
    "UseSameUsername": true|false
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

