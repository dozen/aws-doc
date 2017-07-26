[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-credential-report:


*********************
get-credential-report
*********************



===========
Description
===========



Retrieves a credential report for the AWS account. For more information about the credential report, see `Getting Credential Reports`_ in the *IAM User Guide* . 



========
Synopsis
========

::

    get-credential-report
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get a credential report**

This example opens the returned report and outputs it to the pipeline as an array of text lines::

  aws iam get-credential-report

Output::

  {
      "GeneratedTime":  "2015-06-17T19:11:50Z",
	  "ReportFormat": "text/csv"
  }

For more information, see `Getting Credential Reports for Your AWS Account`_ in the *Using IAM* guide.

.. _`Getting Credential Reports for Your AWS Account`: http://docs.aws.amazon.com/IAM/latest/UserGuide/credential-reports.html

======
Output
======

Content -> (blob)

  

  Contains the credential report. The report is Base64-encoded.

  

  

ReportFormat -> (string)

  

  The format (MIME type) of the credential report.

  

  

GeneratedTime -> (timestamp)

  

  The date and time when the credential report was created, in `ISO 8601 date-time format`_ . 

  

  



.. _ISO 8601 date-time format: http://www.iso.org/iso/iso8601
.. _Getting Credential Reports: http://docs.aws.amazon.com/IAM/latest/UserGuide/credential-reports.html
