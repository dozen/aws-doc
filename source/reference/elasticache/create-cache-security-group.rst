[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache create-cache-security-group:


***************************
create-cache-security-group
***************************



===========
Description
===========



Creates a new cache security group. Use a cache security group to control access to one or more cache clusters.

 

Cache security groups are only used when you are creating a cache cluster outside of an Amazon Virtual Private Cloud (Amazon VPC). If you are creating a cache cluster inside of a VPC, use a cache subnet group instead. For more information, see `create-cache-subnet-group <http://docs.aws.amazon.com/AmazonElastiCache/latest/APIReference/API_CreateCacheSubnetGroup.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticache-2015-02-02/CreateCacheSecurityGroup>`_


========
Synopsis
========

::

    create-cache-security-group
  --cache-security-group-name <value>
  --description <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cache-security-group-name`` (string)


  A name for the cache security group. This value is stored as a lowercase string.

   

  Constraints: Must contain no more than 255 alphanumeric characters. Cannot be the word "Default".

   

  Example: ``mysecuritygroup``  

  

``--description`` (string)


  A description for the cache security group.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

CacheSecurityGroup -> (structure)

  

  Represents the output of one of the following operations:

   

   
  * ``authorize-cache-security-group-ingress``   
   
  * ``create-cache-security-group``   
   
  * ``revoke-cache-security-group-ingress``   
   

  

  OwnerId -> (string)

    

    The AWS account ID of the cache security group owner.

    

    

  CacheSecurityGroupName -> (string)

    

    The name of the cache security group.

    

    

  Description -> (string)

    

    The description of the cache security group.

    

    

  EC2SecurityGroups -> (list)

    

    A list of Amazon EC2 security groups that are associated with this cache security group.

    

    (structure)

      

      Provides ownership and status information for an Amazon EC2 security group.

      

      Status -> (string)

        

        The status of the Amazon EC2 security group.

        

        

      EC2SecurityGroupName -> (string)

        

        The name of the Amazon EC2 security group.

        

        

      EC2SecurityGroupOwnerId -> (string)

        

        The AWS account ID of the Amazon EC2 security group owner.

        

        

      

    

  

