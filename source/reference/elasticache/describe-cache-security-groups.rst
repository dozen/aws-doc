[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache describe-cache-security-groups:


******************************
describe-cache-security-groups
******************************



===========
Description
===========



The *describe-cache-security-groups* action returns a list of cache security group descriptions. If a cache security group name is specified, the list will contain only the description of that group.



``describe-cache-security-groups`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``CacheSecurityGroups``


========
Synopsis
========

::

    describe-cache-security-groups
  [--cache-security-group-name <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cache-security-group-name`` (string)


  The name of the cache security group to return details for.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Marker -> (string)

  

  Provides an identifier to allow retrieval of paginated results.

  

  

CacheSecurityGroups -> (list)

  

  A list of cache security groups. Each element in the list contains detailed information about one group.

  

  (structure)

    

    Represents the output of one of the following actions:

     

     
    * *authorize-cache-security-group-ingress*  
     
    * *create-cache-security-group*  
     
    * *revoke-cache-security-group-ingress*  
     

    

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

          

          

        

      

    

  

