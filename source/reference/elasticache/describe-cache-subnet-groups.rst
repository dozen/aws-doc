[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache describe-cache-subnet-groups:


****************************
describe-cache-subnet-groups
****************************



===========
Description
===========



The *describe-cache-subnet-groups* action returns a list of cache subnet group descriptions. If a subnet group name is specified, the list will contain only the description of that group.



``describe-cache-subnet-groups`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``CacheSubnetGroups``


========
Synopsis
========

::

    describe-cache-subnet-groups
  [--cache-subnet-group-name <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cache-subnet-group-name`` (string)


  The name of the cache subnet group to return details for.

  

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

  

  

CacheSubnetGroups -> (list)

  

  A list of cache subnet groups. Each element in the list contains detailed information about one group.

  

  (structure)

    

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

            

            

          

        

      

    

  

