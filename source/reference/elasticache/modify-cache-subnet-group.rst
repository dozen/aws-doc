[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache modify-cache-subnet-group:


*************************
modify-cache-subnet-group
*************************



===========
Description
===========



The *modify-cache-subnet-group* action modifies an existing cache subnet group.



========
Synopsis
========

::

    modify-cache-subnet-group
  --cache-subnet-group-name <value>
  [--cache-subnet-group-description <value>]
  [--subnet-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cache-subnet-group-name`` (string)


  The name for the cache subnet group. This value is stored as a lowercase string.

   

  Constraints: Must contain no more than 255 alphanumeric characters or hyphens.

   

  Example: ``mysubnetgroup`` 

  

``--cache-subnet-group-description`` (string)


  A description for the cache subnet group.

  

``--subnet-ids`` (list)


  The EC2 subnet IDs for the cache subnet group.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

CacheSubnetGroup -> (structure)

  

  Represents the output of one of the following actions:

   

   
  * *create-cache-subnet-group*  
   
  * *modify-cache-subnet-group*  
   

  

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

          

          

        

      

    

  

