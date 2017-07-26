[ :ref:`aws <cli:aws>` . :ref:`lightsail <cli:aws lightsail>` ]

.. _cli:aws lightsail put-instance-public-ports:


*************************
put-instance-public-ports
*************************



===========
Description
===========



Sets the specified open ports for an Amazon Lightsail instance, and closes all ports for every protocol not included in the current request.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lightsail-2016-11-28/PutInstancePublicPorts>`_


========
Synopsis
========

::

    put-instance-public-ports
  --port-infos <value>
  --instance-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--port-infos`` (list)


  Specifies information about the public port(s).

  



Shorthand Syntax::

    fromPort=integer,toPort=integer,protocol=string ...




JSON Syntax::

  [
    {
      "fromPort": integer,
      "toPort": integer,
      "protocol": "tcp"|"all"|"udp"
    }
    ...
  ]



``--instance-name`` (string)


  The Lightsail instance name of the public port(s) you are setting.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

operation -> (structure)

  

  Describes metadata about the operation you just executed.

  

  id -> (string)

    

    The ID of the operation.

    

    

  resourceName -> (string)

    

    The resource name.

    

    

  resourceType -> (string)

    

    The resource type. 

    

    

  createdAt -> (timestamp)

    

    The timestamp when the operation was initialized (e.g., ``1479816991.349`` ).

    

    

  location -> (structure)

    

    The region and Availability Zone.

    

    availabilityZone -> (string)

      

      The Availability Zone. Follows the format ``us-east-1a`` (case-sensitive).

      

      

    regionName -> (string)

      

      The AWS Region name.

      

      

    

  isTerminal -> (boolean)

    

    A Boolean value indicating whether the operation is terminal.

    

    

  operationDetails -> (string)

    

    Details about the operation (e.g., ``Debian-1GB-Virginia-1`` ).

    

    

  operationType -> (string)

    

    The type of operation. 

    

    

  status -> (string)

    

    The status of the operation. 

    

    

  statusChangedAt -> (timestamp)

    

    The timestamp when the status was changed (e.g., ``1479816991.349`` ).

    

    

  errorCode -> (string)

    

    The error code.

    

    

  errorDetails -> (string)

    

    The error details.

    

    

  

