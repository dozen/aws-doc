[ :ref:`aws <cli:aws>` . :ref:`greengrass <cli:aws greengrass>` ]

.. _cli:aws greengrass get-connectivity-info:


*********************
get-connectivity-info
*********************



===========
Description
===========

Retrieves the connectivity information for a core.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/greengrass-2017-06-07/GetConnectivityInfo>`_


========
Synopsis
========

::

    get-connectivity-info
  --thing-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--thing-name`` (string)
Thing Name

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ConnectivityInfo -> (list)

  Connectivity info array

  (structure)

    Connectivity Info

    HostAddress -> (string)

      Endpoint for the GGC. Can be an IP address or DNS.

      

    Id -> (string)

      Element Id for this entry in the list.

      

    Metadata -> (string)

      Metadata for this endpoint.

      

    PortNumber -> (integer)

      Port of the GGC. Usually 8883.

      

    

  

Message -> (string)

  Response Text

  

