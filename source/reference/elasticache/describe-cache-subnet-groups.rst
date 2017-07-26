[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache describe-cache-subnet-groups:


****************************
describe-cache-subnet-groups
****************************



===========
Description
===========



Returns a list of cache subnet group descriptions. If a subnet group name is specified, the list contains only the description of that group.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticache-2015-02-02/DescribeCacheSubnetGroups>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cache-subnet-group-name`` (string)


  The name of the cache subnet group to return details for.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Marker -> (string)

  

  Provides an identifier to allow retrieval of paginated results.

  

  

CacheSubnetGroups -> (list)

  

  A list of cache subnet groups. Each element in the list contains detailed information about one group.

  

  (structure)

    

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

            

            

          

        

      

    

  

