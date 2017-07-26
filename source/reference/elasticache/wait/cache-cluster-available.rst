[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` . :ref:`wait <cli:aws elasticache wait>` ]

.. _cli:aws elasticache wait cache-cluster-available:


***********************
cache-cluster-available
***********************



===========
Description
===========

Wait until JMESPath query CacheClusters[].CacheClusterStatus returns available for all elements when polling with ``describe-cache-clusters``. It will poll every 30 seconds until a successful state has been reached. This will exit with a return code of 255 after 60 failed checks.

``cache-cluster-available`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``CacheClusters``


========
Synopsis
========

::

    cache-cluster-available
  [--cache-cluster-id <value>]
  [--show-cache-node-info | --no-show-cache-node-info]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cache-cluster-id`` (string)


  The user-supplied cluster identifier. If this parameter is specified, only information about that specific cache cluster is returned. This parameter isn't case sensitive.

  

``--show-cache-node-info`` | ``--no-show-cache-node-info`` (boolean)


  An optional flag that can be included in the DescribeCacheCluster request to retrieve information about the individual cache nodes.

  

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

None