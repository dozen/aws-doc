[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector register-cross-account-access-role:


**********************************
register-cross-account-access-role
**********************************



===========
Description
===========



Registers the IAM role that Amazon Inspector uses to list your EC2 instances at the start of the assessment run or when you call the  preview-agents action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/inspector-2016-02-16/RegisterCrossAccountAccessRole>`_


========
Synopsis
========

::

    register-cross-account-access-role
  --role-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--role-arn`` (string)


  The ARN of the IAM role that Amazon Inspector uses to list your EC2 instances during the assessment run or when you call the  preview-agents action. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To register the cross account access role**

The following ``register-cross-account-access-role`` command registers the IAM role with the ARN of  ``arn:aws:iam::123456789012:role/inspector`` that Amazon Inspector uses to list your EC2 instances at the start of the assessment run of when you call the preview-agents command::

  aws inspector register-cross-account-access-role --role-arn arn:aws:iam::123456789012:role/inspector

For more information, see `Setting up Amazon Inspector`_ in the *Amazon Inspector* guide.

.. _`Setting up Amazon Inspector`: https://docs.aws.amazon.com/inspector/latest/userguide/inspector_settingup.html



======
Output
======

None