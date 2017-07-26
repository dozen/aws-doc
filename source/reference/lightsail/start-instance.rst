[ :ref:`aws <cli:aws>` . :ref:`lightsail <cli:aws lightsail>` ]

.. _cli:aws lightsail start-instance:


**************
start-instance
**************



===========
Description
===========



Starts a specific Amazon Lightsail instance from a stopped state. To restart an instance, use the reboot instance operation.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lightsail-2016-11-28/StartInstance>`_


========
Synopsis
========

::

    start-instance
  --instance-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-name`` (string)


  The name of the instance (a virtual private server) to start.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

operations -> (list)

  

  An array of key-value pairs containing information about the request operation.

  

  (structure)

    

    Describes the API operation.

    

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

      

      

    

  

