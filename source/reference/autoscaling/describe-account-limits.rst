[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling describe-account-limits:


***********************
describe-account-limits
***********************



===========
Description
===========



Describes the current Auto Scaling resource limits for your AWS account.

 

For information about requesting an increase in these limits, see `AWS Service Limits`_ in the *Amazon Web Services General Reference* .



========
Synopsis
========

::

    describe-account-limits
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

**To describe your Auto Scaling account limits**

This example describes the Auto Scaling limits for your AWS account::

	aws autoscaling describe-account-limits

The following is example output::

	{
	  "NumberOfLaunchConfigurations": 5,
		"MaxNumberOfLaunchConfigurations": 100,
		"NumberOfAutoScalingGroups": 3,
		"MaxNumberOfAutoScalingGroups": 20
	}

For more information, see `Auto Scaling Limits`_ in the *Auto Scaling Developer Guide*.

.. _`Auto Scaling Limits`: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/as-account-limits.html


======
Output
======

MaxNumberOfAutoScalingGroups -> (integer)

  

  The maximum number of groups allowed for your AWS account. The default limit is 20 per region.

  

  

MaxNumberOfLaunchConfigurations -> (integer)

  

  The maximum number of launch configurations allowed for your AWS account. The default limit is 100 per region.

  

  

NumberOfAutoScalingGroups -> (integer)

  

  The current number of groups for your AWS account.

  

  

NumberOfLaunchConfigurations -> (integer)

  

  The current number of launch configurations for your AWS account.

  

  



.. _AWS Service Limits: http://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html
