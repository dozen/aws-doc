[ :ref:`aws <cli:aws>` . :ref:`discovery <cli:aws discovery>` ]

.. _cli:aws discovery start-export-task:


*****************
start-export-task
*****************



===========
Description
===========



Begins the export of discovered data to an S3 bucket.

 

If you specify ``agentId`` in a filter, the task exports up to 72 hours of detailed data collected by the identified Application Discovery Agent, including network, process, and performance details. A time range for exported agent data may be set by using ``startTime`` and ``endTime`` . Export of detailed agent data is limited to five concurrently running exports. 

 

If you do not include an ``agentId`` filter, summary data is exported that includes both AWS Agentless Discovery Connector data and summary data from AWS Discovery Agents. Export of summary data is limited to two exports per day. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/discovery-2015-11-01/StartExportTask>`_


========
Synopsis
========

::

    start-export-task
  [--export-data-format <value>]
  [--filters <value>]
  [--start-time <value>]
  [--end-time <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--export-data-format`` (list)


  The file format for the returned export data. Default value is ``CSV`` .

  



Syntax::

  "string" "string" ...

  Where valid values are:
    CSV
    GRAPHML





``--filters`` (list)


  If a filter is present, it selects the single ``agentId`` of the Application Discovery Agent for which data is exported. The ``agentId`` can be found in the results of the ``describe-agents`` API or CLI. If no filter is present, ``startTime`` and ``endTime`` are ignored and exported data includes both Agentless Discovery Connector data and summary data from Application Discovery agents. 

  



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



``--start-time`` (timestamp)


  The start timestamp for exported data from the single Application Discovery Agent selected in the filters. If no value is specified, data is exported starting from the first data collected by the agent.

  

``--end-time`` (timestamp)


  The end timestamp for exported data from the single Application Discovery Agent selected in the filters. If no value is specified, exported data includes the most recent data collected by the agent.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

exportId -> (string)

  

  A unique identifier used to query the status of an export request.

  

  

