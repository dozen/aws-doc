[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache create-cache-subnet-group:


*************************
create-cache-subnet-group
*************************



===========
Description
===========



Creates a new cache subnet group.

 

Use this parameter only when you are creating a cluster in an Amazon Virtual Private Cloud (Amazon VPC).



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticache-2015-02-02/CreateCacheSubnetGroup>`_


========
Synopsis
========

::

    create-cache-subnet-group
  --cache-subnet-group-name <value>
  --cache-subnet-group-description <value>
  --subnet-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cache-subnet-group-name`` (string)


  A name for the cache subnet group. This value is stored as a lowercase string.

   

  Constraints: Must contain no more than 255 alphanumeric characters or hyphens.

   

  Example: ``mysubnetgroup``  

  

``--cache-subnet-group-description`` (string)


  A description for the cache subnet group.

  

``--subnet-ids`` (list)


  A list of VPC subnet IDs for the cache subnet group.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

CacheSubnetGroup -> (structure)

  

  Represents the output of one of the following operations:

   

   
  * ``create-cache-subnet-group``   
   
  * ``modify-cache-subnet-group``   
   

  

  CacheSubnetGroupName -> (string)

    

    The name of the cache subnet group.

    

    

  CacheSubnetGroupDescription -> (string)

    

    The description of the cache subnet group.

    

    

  VpcId -> (string)

    

    The Amazon Virtual Private Cloud identifier (VPC ID) of the cache subnet group.

    

    

  Subnets -> (list)

    

    A list of subnets associated with the cache subnet group.

    

    (structure)

      

      Represents the subnet associated with a cache cluster. This parameter refers to subnets defined in Amazon Virtual Private Cloud (Amazon VPC) and used with ElastiCache.

      

      SubnetIdentifier -> (string)

        

        The unique identifier for the subnet.

        

        

      SubnetAvailabilityZone -> (structure)

        

        The Availability Zone associated with the subnet.

        

        Name -> (string)

          

          The name of the Availability Zone.

          

          

        

      

    

  

