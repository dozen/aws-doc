[ :ref:`aws <cli:aws>` . :ref:`lightsail <cli:aws lightsail>` ]

.. _cli:aws lightsail close-instance-public-ports:


***************************
close-instance-public-ports
***************************



===========
Description
===========



Closes the public ports on a specific Amazon Lightsail instance.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lightsail-2016-11-28/CloseInstancePublicPorts>`_


========
Synopsis
========

::

    close-instance-public-ports
  --port-info <value>
  --instance-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--port-info`` (structure)


  Information about the public port you are trying to close.

  



Shorthand Syntax::

    fromPort=integer,toPort=integer,protocol=string




JSON Syntax::

  {
    "fromPort": integer,
    "toPort": integer,
    "protocol": "tcp"|"all"|"udp"
  }



``--instance-name`` (string)


  The name of the instance on which you're attempting to close the public ports.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

operation -> (structure)

  

  An array of key-value pairs that contains information about the operation.

  

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

    

    

  

