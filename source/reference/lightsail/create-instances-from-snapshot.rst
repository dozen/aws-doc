[ :ref:`aws <cli:aws>` . :ref:`lightsail <cli:aws lightsail>` ]

.. _cli:aws lightsail create-instances-from-snapshot:


******************************
create-instances-from-snapshot
******************************



===========
Description
===========



Uses a specific snapshot as a blueprint for creating one or more new instances that are based on that identical configuration.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lightsail-2016-11-28/CreateInstancesFromSnapshot>`_


========
Synopsis
========

::

    create-instances-from-snapshot
  --instance-names <value>
  --availability-zone <value>
  --instance-snapshot-name <value>
  --bundle-id <value>
  [--user-data <value>]
  [--key-pair-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-names`` (list)


  The names for your new instances.

  



Syntax::

  "string" "string" ...



``--availability-zone`` (string)


  The Availability Zone where you want to create your instances. Use the following formatting: ``us-east-1a`` (case sensitive). You can get a list of availability zones by using the `get regions <http://docs.aws.amazon.com/lightsail/2016-11-28/api-reference/API_GetRegions.html>`_ operation. Be sure to add the ``include availability zones`` parameter to your request.

  

``--instance-snapshot-name`` (string)


  The name of the instance snapshot on which you are basing your new instances. Use the get instance snapshots operation to return information about your existing snapshots.

  

``--bundle-id`` (string)


  The bundle of specification information for your virtual private server (or *instance* ), including the pricing plan (e.g., ``micro_1_0`` ).

  

``--user-data`` (string)


  You can create a launch script that configures a server with additional user data. For example, ``apt-get –y update`` .

   

  .. note::

     

    Depending on the machine image you choose, the command to get software on your instance varies. Amazon Linux and CentOS use ``yum`` , Debian and Ubuntu use ``apt-get`` , and FreeBSD uses ``pkg`` . For a complete list, see the `Dev Guide <http://lightsail.aws.amazon.com/ls/docs/getting-started/articles/pre-installed-apps>`_ .

     

  

``--key-pair-name`` (string)


  The name for your key pair.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON availability-zone provided. The JSON availability-zone follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

operations -> (list)

  

  An array of key-value pairs containing information about the results of your create instances from snapshot request.

  

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

      

      

    

  

