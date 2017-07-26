[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector describe-cross-account-access-role:


**********************************
describe-cross-account-access-role
**********************************



===========
Description
===========



Describes the IAM role that enables Amazon Inspector to access your AWS account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/inspector-2016-02-16/DescribeCrossAccountAccessRole>`_


========
Synopsis
========

::

    describe-cross-account-access-role
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

**To describe the cross account access role**

The following ``describe-cross-account-access-role`` command describes the IAM role that enables Amazon Inspector to access your AWS account::

  aws inspector describe-cross-account-access-role

Output::

 {
	 "registeredAt": 1458069182.826,
	 "roleArn": "arn:aws:iam::123456789012:role/inspector",
	 "valid": true
 } 

For more information, see `Setting up Amazon Inspector`_ in the *Amazon Inspector* guide.

.. _`Setting up Amazon Inspector`: https://docs.aws.amazon.com/inspector/latest/userguide/inspector_settingup.html



======
Output
======

roleArn -> (string)

  

  The ARN that specifies the IAM role that Amazon Inspector uses to access your AWS account.

  

  

valid -> (boolean)

  

  A Boolean value that specifies whether the IAM role has the necessary policies attached to enable Amazon Inspector to access your AWS account.

  

  

registeredAt -> (timestamp)

  

  The date when the cross-account access role was registered.

  

  

