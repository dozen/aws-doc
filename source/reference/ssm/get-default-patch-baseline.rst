[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm get-default-patch-baseline:


**************************
get-default-patch-baseline
**************************



===========
Description
===========



Retrieves the default patch baseline. Note that Systems Manager supports creating multiple default patch baselines. For example, you can create a default patch baseline for each operating system.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/GetDefaultPatchBaseline>`_


========
Synopsis
========

::

    get-default-patch-baseline
  [--operating-system <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--operating-system`` (string)


  Returns the default patch baseline for the specified operating system.

  

  Possible values:

  
  *   ``WINDOWS``

  
  *   ``AMAZON_LINUX``

  
  *   ``UBUNTU``

  
  *   ``REDHAT_ENTERPRISE_LINUX``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To display the default patch baseline**

This example displays the default patch baseline.

Command::

  aws ssm get-default-patch-baseline

Output::

  {
    "BaselineId":"arn:aws:ssm:us-west-1:812345678901:patchbaseline/pb-0ca44a362f8afc725"
  }


======
Output
======

BaselineId -> (string)

  

  The ID of the default patch baseline.

  

  

OperatingSystem -> (string)

  

  The operating system for the returned patch baseline. 

  

  

