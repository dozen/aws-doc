[ :ref:`aws <cli:aws>` . :ref:`datapipeline <cli:aws datapipeline>` ]

.. _cli:aws datapipeline list-pipelines:


**************
list-pipelines
**************



===========
Description
===========



Lists the pipeline identifiers for all active pipelines that you have permission to access.



``list-pipelines`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``pipelineIdList``


========
Synopsis
========

::

    list-pipelines
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON marker provided. The JSON marker follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To list your pipelines**

This example lists your pipelines::

   aws datapipeline list-pipelines
   
The following is example output::

  {
    "pipelineIdList": [
        {
            "id": "df-00627471SOVYZEXAMPLE",
            "name": "my-pipeline"
        },
        {
            "id": "df-09028963KNVMREXAMPLE",
            "name": "ImportDDB"
        },
        {
            "id": "df-0870198233ZYVEXAMPLE",
            "name": "CrossRegionDDB"
        },
        {
            "id": "df-00189603TB4MZEXAMPLE",
            "name": "CopyRedshift"
        }
    ]
  }


======
Output
======

pipelineIdList -> (list)

  

  The pipeline identifiers. If you require additional information about the pipelines, you can use these identifiers to call  describe-pipelines and  get-pipeline-definition .

  

  (structure)

    

    Contains the name and identifier of a pipeline.

    

    id -> (string)

      

      The ID of the pipeline that was assigned by AWS Data Pipeline. This is a marker of the form ``df-297EG78HU43EEXAMPLE`` .

      

      

    name -> (string)

      

      The name of the pipeline.

      

      

    

  

marker -> (string)

  

  The starting point for the next page of results. To view the next page of results, call ``ListPipelinesOutput`` again with this marker value. If the value is null, there are no more results.

  

  

hasMoreResults -> (boolean)

  

  Indicates whether there are more results that can be obtained by a subsequent call.

  

  

