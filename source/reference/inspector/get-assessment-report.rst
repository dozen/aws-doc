[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector get-assessment-report:


*********************
get-assessment-report
*********************



===========
Description
===========



Produces an assessment report that includes detailed and comprehensive results of a specified assessment run. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/inspector-2016-02-16/GetAssessmentReport>`_


========
Synopsis
========

::

    get-assessment-report
  --assessment-run-arn <value>
  --report-file-format <value>
  --report-type <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--assessment-run-arn`` (string)


  The ARN that specifies the assessment run for which you want to generate a report.

  

``--report-file-format`` (string)


  Specifies the file format (html or pdf) of the assessment report that you want to generate.

  

  Possible values:

  
  *   ``HTML``

  
  *   ``PDF``

  

  

``--report-type`` (string)


  Specifies the type of the assessment report that you want to generate. There are two types of assessment reports: a finding report and a full report. For more information, see `Assessment Reports <http://docs.aws.amazon.com/inspector/latest/userguide/inspector_reports.html>`_ . 

  

  Possible values:

  
  *   ``FINDING``

  
  *   ``FULL``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

status -> (string)

  

  Specifies the status of the request to generate an assessment report. 

  

  

url -> (string)

  

  Specifies the URL where you can find the generated assessment report. This parameter is only returned if the report is successfully generated.

  

  

