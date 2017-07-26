[ :ref:`aws <cli:aws>` . :ref:`cur <cli:aws cur>` ]

.. _cli:aws cur put-report-definition:


*********************
put-report-definition
*********************



===========
Description
===========

Create a new report definition

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cur-2017-01-06/PutReportDefinition>`_


========
Synopsis
========

::

    put-report-definition
  --report-definition <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--report-definition`` (structure)
The definition of AWS Cost and Usage Report. Customer can specify the report name, time unit, report format, compression format, S3 bucket and additional artifacts and schema elements in the definition.



Shorthand Syntax::

    ReportName=string,TimeUnit=string,Format=string,Compression=string,AdditionalSchemaElements=string,string,S3Bucket=string,S3Prefix=string,S3Region=string,AdditionalArtifacts=string,string




JSON Syntax::

  {
    "ReportName": "string",
    "TimeUnit": "HOURLY"|"DAILY",
    "Format": "textORcsv",
    "Compression": "ZIP"|"GZIP",
    "AdditionalSchemaElements": ["RESOURCES", ...],
    "S3Bucket": "string",
    "S3Prefix": "string",
    "S3Region": "us-east-1"|"us-west-1"|"us-west-2"|"eu-central-1"|"eu-west-1"|"ap-southeast-1"|"ap-southeast-2"|"ap-northeast-1",
    "AdditionalArtifacts": ["REDSHIFT"|"QUICKSIGHT", ...]
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

