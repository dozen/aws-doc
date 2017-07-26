[ :ref:`aws <cli:aws>` . :ref:`dms <cli:aws dms>` ]

.. _cli:aws dms create-replication-subnet-group:


*******************************
create-replication-subnet-group
*******************************



===========
Description
===========



Creates a replication subnet group given a list of the subnet IDs in a VPC.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dms-2016-01-01/CreateReplicationSubnetGroup>`_


========
Synopsis
========

::

    create-replication-subnet-group
  --replication-subnet-group-identifier <value>
  --replication-subnet-group-description <value>
  --subnet-ids <value>
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--replication-subnet-group-identifier`` (string)


  The name for the replication subnet group. This value is stored as a lowercase string.

   

  Constraints: Must contain no more than 255 alphanumeric characters, periods, spaces, underscores, or hyphens. Must not be "default".

   

  Example: ``mySubnetgroup``  

  

``--replication-subnet-group-description`` (string)


  The description for the subnet group.

  

``--subnet-ids`` (list)


  The EC2 subnet IDs for the subnet group.

  



Syntax::

  "string" "string" ...



``--tags`` (list)


  The tag to be assigned to the subnet group.

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
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

ReplicationSubnetGroup -> (structure)

  

  The replication subnet group that was created.

  

  ReplicationSubnetGroupIdentifier -> (string)

    

    The identifier of the replication instance subnet group.

    

    

  ReplicationSubnetGroupDescription -> (string)

    

    The description of the replication subnet group.

    

    

  VpcId -> (string)

    

    The ID of the VPC.

    

    

  SubnetGroupStatus -> (string)

    

    The status of the subnet group.

    

    

  Subnets -> (list)

    

    The subnets that are in the subnet group.

    

    (structure)

      

      

      

      SubnetIdentifier -> (string)

        

        The subnet identifier.

        

        

      SubnetAvailabilityZone -> (structure)

        

        The Availability Zone of the subnet.

        

        Name -> (string)

          

          The name of the availability zone.

          

          

        

      SubnetStatus -> (string)

        

        The status of the subnet.

        

        

      

    

  

