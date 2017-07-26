[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice start-configuration-recorder:


****************************
start-configuration-recorder
****************************



===========
Description
===========



Starts recording configurations of the AWS resources you have selected to record in your AWS account.

 

You must have created at least one delivery channel to successfully start the configuration recorder.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/config-2014-11-12/StartConfigurationRecorder>`_


========
Synopsis
========

::

    start-configuration-recorder
  --configuration-recorder-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--configuration-recorder-name`` (string)


  The name of the recorder object that records each configuration change made to the resources.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========


**To start the configuration recorder**

The following command starts the default configuration recorder::

    aws configservice start-configuration-recorder --configuration-recorder-name default

If the command succeeds, AWS Config returns no output. To verify that AWS Config is recording your resources, run the `get-status`__ command.

.. __: http://docs.aws.amazon.com/cli/latest/reference/configservice/get-status.html

======
Output
======

None