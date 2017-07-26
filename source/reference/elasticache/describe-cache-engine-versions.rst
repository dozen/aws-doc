[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache describe-cache-engine-versions:


******************************
describe-cache-engine-versions
******************************



===========
Description
===========



Returns a list of the available cache engines and their versions.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticache-2015-02-02/DescribeCacheEngineVersions>`_


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
  [--generate-cli-skeleton <value>]




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

   

  Valid values are: ``memcached1.4`` | ``redis2.6`` | ``redis2.8`` | ``redis3.2``  

   

  Constraints:

   

   
  * Must be 1 to 255 alphanumeric characters 
   
  * First character must be a letter 
   
  * Cannot end with a hyphen or contain two consecutive hyphens 
   

  

``--default-only`` | ``--no-default-only`` (boolean)


  If ``true`` , specifies that only the default version of the specified engine or engine and major version combination is to be returned.

  

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

       

      Valid values are: ``memcached1.4`` | ``redis2.6`` | ``redis2.8`` | ``redis3.2``  

      

      

    CacheEngineDescription -> (string)

      

      The description of the cache engine.

      

      

    CacheEngineVersionDescription -> (string)

      

      The description of the cache engine version.

      

      

    

  

