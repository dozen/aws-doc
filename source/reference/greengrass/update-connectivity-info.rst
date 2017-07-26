[ :ref:`aws <cli:aws>` . :ref:`greengrass <cli:aws greengrass>` ]

.. _cli:aws greengrass update-connectivity-info:


************************
update-connectivity-info
************************



===========
Description
===========

Updates the connectivity information for the core. Any devices that belong to the group which has this core will receive this information in order to find the location of the core and connect to it.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/greengrass-2017-06-07/UpdateConnectivityInfo>`_


========
Synopsis
========

::

    update-connectivity-info
  [--connectivity-info <value>]
  --thing-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--connectivity-info`` (list)
Connectivity info array



Shorthand Syntax::

    HostAddress=string,Id=string,Metadata=string,PortNumber=integer ...




JSON Syntax::

  [
    {
      "HostAddress": "string",
      "Id": "string",
      "Metadata": "string",
      "PortNumber": integer
    }
    ...
  ]



``--thing-name`` (string)
Thing Name

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Message -> (string)

  Response Text

  

Version -> (string)

  New Version

  

