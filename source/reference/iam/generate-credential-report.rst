[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam generate-credential-report:


**************************
generate-credential-report
**************************



===========
Description
===========



Generates a credential report for the AWS account. For more information about the credential report, see `Getting Credential Reports <http://docs.aws.amazon.com/IAM/latest/UserGuide/credential-reports.html>`_ in the *IAM User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/GenerateCredentialReport>`_


========
Synopsis
========

::

    generate-credential-report
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To generate a credential report**

The following example attempts to generate a credential report for the AWS account::

  aws iam generate-credential-report

Output::

  {
      "State":  "STARTED",
	  "Description": "No report exists. Starting a new report generation task"
  }

For more information, see `Getting Credential Reports for Your AWS Account`_ in the *Using IAM* guide.

.. _`Getting Credential Reports for Your AWS Account`: http://docs.aws.amazon.com/IAM/latest/UserGuide/credential-reports.html

======
Output
======

State -> (string)

  

  Information about the state of the credential report.

  

  

Description -> (string)

  

  Information about the credential report.

  

  

