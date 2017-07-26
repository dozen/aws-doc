[ :ref:`aws <cli:aws>` . :ref:`datapipeline <cli:aws datapipeline>` ]

.. _cli:aws datapipeline query-objects:


*************
query-objects
*************



===========
Description
===========



Queries the specified pipeline for the names of objects that match the specified set of conditions.



``query-objects`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ids``


========
Synopsis
========

::

    query-objects
  --pipeline-id <value>
  --sphere <value>
  [--objects-query <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--pipeline-id`` (string)


  The ID of the pipeline.

  

``--sphere`` (string)


  Indicates whether the query applies to components or instances. The possible values are: ``COMPONENT`` , ``INSTANCE`` , and ``ATTEMPT`` .

  

``--objects-query`` (structure)


  The query that defines the objects to be returned. The ``objects-query`` object can contain a maximum of ten selectors. The conditions in the query are limited to top-level String fields in the object. These filters can be applied to components, instances, and attempts.

  



JSON Syntax::

  {
    "selectors": [
      {
        "fieldName": "string",
        "operator": {
          "type": "EQ"|"REF_EQ"|"LE"|"GE"|"BETWEEN",
          "values": ["string", ...]
        }
      }
      ...
    ]
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON marker provided. The JSON marker follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

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

ids -> (list)

  

  The identifiers that match the query selectors.

  

  (string)

    

    

  

marker -> (string)

  

  The starting point for the next page of results. To view the next page of results, call ``query-objects`` again with this marker value. If the value is null, there are no more results.

  

  

hasMoreResults -> (boolean)

  

  Indicates whether there are more results that can be obtained by a subsequent call.

  

  

