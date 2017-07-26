[ :ref:`aws <cli:aws>` . :ref:`discovery <cli:aws discovery>` ]

.. _cli:aws discovery describe-export-configurations:


******************************
describe-export-configurations
******************************



===========
Description
===========



Deprecated. Use ``describe-export-tasks`` instead.

 

Retrieves the status of a given export process. You can retrieve status from a maximum of 100 processes.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/discovery-2015-11-01/DescribeExportConfigurations>`_


========
Synopsis
========

::

    describe-export-configurations
  [--export-ids <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--export-ids`` (list)


  A unique identifier that you can use to query the export status.

  



Syntax::

  "string" "string" ...



``--max-results`` (integer)


  The maximum number of results that you want to display as a part of the query.

  

``--next-token`` (string)


  A token to get the next set of results. For example, if you specify 100 IDs for ``DescribeExportConfigurationsRequest$exportIds`` but set ``DescribeExportConfigurationsRequest$maxResults`` to 10, you get results in a set of 10. Use the token in the query to get the next set of 10.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

exportsInfo -> (list)

  

  Returns export details. When the status is complete, the response includes a URL for an Amazon S3 bucket where you can view the data in a CSV file.

  

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

  

  A token to get the next set of results. For example, if you specify 100 IDs for ``DescribeExportConfigurationsRequest$exportIds`` but set ``DescribeExportConfigurationsRequest$maxResults`` to 10, you get results in a set of 10. Use the token in the query to get the next set of 10.

  

  

