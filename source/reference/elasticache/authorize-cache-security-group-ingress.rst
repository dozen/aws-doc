[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache authorize-cache-security-group-ingress:


**************************************
authorize-cache-security-group-ingress
**************************************



===========
Description
===========



Allows network ingress to a cache security group. Applications using ElastiCache must be running on Amazon EC2, and Amazon EC2 security groups are used as the authorization mechanism.

 

.. note::

   

  You cannot authorize ingress from an Amazon EC2 security group in one region to an ElastiCache cluster in another region.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticache-2015-02-02/AuthorizeCacheSecurityGroupIngress>`_


========
Synopsis
========

::

    authorize-cache-security-group-ingress
  --cache-security-group-name <value>
  --ec2-security-group-name <value>
  --ec2-security-group-owner-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cache-security-group-name`` (string)


  The cache security group that allows network ingress.

  

``--ec2-security-group-name`` (string)


  The Amazon EC2 security group to be authorized for ingress to the cache security group.

  

``--ec2-security-group-owner-id`` (string)


  The AWS account number of the Amazon EC2 security group owner. Note that this is not the same thing as an AWS access key ID - you must provide a valid AWS account number for this parameter.

  

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

        

        

      

    

  

