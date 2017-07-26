[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice stop-configuration-recorder:


***************************
stop-configuration-recorder
***************************



===========
Description
===========



Stops recording configurations of the AWS resources you have selected to record in your AWS account.



========
Synopsis
========

::

    stop-configuration-recorder
  --configuration-recorder-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--configuration-recorder-name`` (string)


  The name of the recorder object that records each configuration change made to the resources.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To stop the configuration recorder**

The following command stops the default configuration recorder::

    aws configservice stop-configuration-recorder --configuration-recorder-name default

If the command succeeds, AWS Config returns no output. To verify that AWS Config is not recording your resources, run the `get-status`__ command.

.. __: http://docs.aws.amazon.com/cli/latest/reference/configservice/get-status.html

======
Output
======

None