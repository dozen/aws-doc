[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling describe-account-limits:


***********************
describe-account-limits
***********************



===========
Description
===========



Describes the current Auto Scaling resource limits for your AWS account.

 

For information about requesting an increase in these limits, see `AWS Service Limits <http://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html>`_ in the *Amazon Web Services General Reference* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/DescribeAccountLimits>`_


========
Synopsis
========

::

    describe-account-limits
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

  

  

