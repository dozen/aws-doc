[ :ref:`aws <cli:aws>` . :ref:`discovery <cli:aws discovery>` ]

.. _cli:aws discovery describe-export-tasks:


*********************
describe-export-tasks
*********************



===========
Description
===========



Retrieve status of one or more export tasks. You can retrieve the status of up to 100 export tasks.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/discovery-2015-11-01/DescribeExportTasks>`_


========
Synopsis
========

::

    describe-export-tasks
  [--export-ids <value>]
  [--filters <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--export-ids`` (list)


  One or more unique identifiers used to query the status of an export request.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters.

   

   
  * ``AgentId`` - ID of the agent whose collected data will be exported 
   

  



Shorthand Syntax::

    name=string,values=string,string,condition=string ...




JSON Syntax::

  [
    {
      "name": "string",
      "values": ["string", ...],
      "condition": "string"
    }
    ...
  ]



``--max-results`` (integer)


  The maximum number of volume results returned by ``describe-export-tasks`` in paginated output. When this parameter is used, ``describe-export-tasks`` only returns ``maxResults`` results in a single page along with a ``nextToken`` response element.

  

``--next-token`` (string)


  The ``nextToken`` value returned from a previous paginated ``describe-export-tasks`` request where ``maxResults`` was used and the results exceeded the value of that parameter. Pagination continues from the end of the previous results that returned the ``nextToken`` value. This value is null when there are no more results to return.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

exportsInfo -> (list)

  

  Contains one or more sets of export request details. When the status of a request is ``SUCCEEDED`` , the response includes a URL for an Amazon S3 bucket where you can view the data in a CSV file.

  

  (structure)

    

    Information regarding the export status of discovered data. The value is an array of objects.

    

    exportId -> (string)

      

      A unique identifier used to query an export.

      

      

    exportStatus -> (string)

      

      The status of the data export job.

      

      

    statusMessage -> (string)

      

      A status message provided for API callers.

      

      

    configurationsDownloadUrl -> (string)

      

      A URL for an Amazon S3 bucket where you can review the exported data. The URL is displayed only if the export succeeded.

      

      

    exportRequestTime -> (timestamp)

      

      The time that the data export was initiated.

      

      

    isTruncated -> (boolean)

      

      If true, the export of agent information exceeded the size limit for a single export and the exported data is incomplete for the requested time range. To address this, select a smaller time range for the export by using ``startDate`` and ``endDate`` .

      

      

    requestedStartTime -> (timestamp)

      

      The value of ``startTime`` parameter in the ``start-export-task`` request. If no ``startTime`` was requested, this result does not appear in ``ExportInfo`` .

      

      

    requestedEndTime -> (timestamp)

      

      The ``endTime`` used in the ``start-export-task`` request. If no ``endTime`` was requested, this result does not appear in ``ExportInfo`` .

      

      

    

  

nextToken -> (string)

  

  The ``nextToken`` value to include in a future ``describe-export-tasks`` request. When the results of a ``describe-export-tasks`` request exceed ``maxResults`` , this value can be used to retrieve the next page of results. This value is null when there are no more results to return.

  

  

