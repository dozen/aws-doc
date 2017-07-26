[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache describe-cache-parameter-groups:


*******************************
describe-cache-parameter-groups
*******************************



===========
Description
===========



The *describe-cache-parameter-groups* action returns a list of cache parameter group descriptions. If a cache parameter group name is specified, the list will contain only the descriptions for that group.



``describe-cache-parameter-groups`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``CacheParameterGroups``


========
Synopsis
========

::

    describe-cache-parameter-groups
  [--cache-parameter-group-name <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cache-parameter-group-name`` (string)


  The name of a specific cache parameter group to return details for.

  

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

  

  

CacheParameterGroups -> (list)

  

  A list of cache parameter groups. Each element in the list contains detailed information about one cache parameter group.

  

  (structure)

    

    Represents the output of a *create-cache-parameter-group* action.

    

    CacheParameterGroupName -> (string)

      

      The name of the cache parameter group.

      

      

    CacheParameterGroupFamily -> (string)

      

      The name of the cache parameter group family that this cache parameter group is compatible with.

      

      

    Description -> (string)

      

      The description for this cache parameter group.

      

      

    

  

