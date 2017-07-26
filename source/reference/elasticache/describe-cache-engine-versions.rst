[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache describe-cache-engine-versions:


******************************
describe-cache-engine-versions
******************************



===========
Description
===========



The *describe-cache-engine-versions* action returns a list of the available cache engines and their versions.



``describe-cache-engine-versions`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``CacheEngineVersions``


========
Synopsis
========

::

    describe-cache-engine-versions
  [--engine <value>]
  [--engine-version <value>]
  [--cache-parameter-group-family <value>]
  [--default-only | --no-default-only]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--engine`` (string)


  The cache engine to return. Valid values: ``memcached`` | ``redis`` 

  

``--engine-version`` (string)


  The cache engine version to return.

   

  Example: ``1.4.14`` 

  

``--cache-parameter-group-family`` (string)


  The name of a specific cache parameter group family to return details for.

   

  Constraints:

   

   
  * Must be 1 to 255 alphanumeric characters
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   

  

``--default-only`` | ``--no-default-only`` (boolean)


  If *true* , specifies that only the default version of the specified engine or engine and major version combination is to be returned.

  

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

  

  

CacheEngineVersions -> (list)

  

  A list of cache engine version details. Each element in the list contains detailed information about one cache engine version.

  

  (structure)

    

    Provides all of the details about a particular cache engine version.

    

    Engine -> (string)

      

      The name of the cache engine.

      

      

    EngineVersion -> (string)

      

      The version number of the cache engine.

      

      

    CacheParameterGroupFamily -> (string)

      

      The name of the cache parameter group family associated with this cache engine.

      

      

    CacheEngineDescription -> (string)

      

      The description of the cache engine.

      

      

    CacheEngineVersionDescription -> (string)

      

      The description of the cache engine version.

      

      

    

  

