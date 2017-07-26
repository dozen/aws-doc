[ :ref:`aws <cli:aws>` . :ref:`batch <cli:aws batch>` ]

.. _cli:aws batch deregister-job-definition:


*************************
deregister-job-definition
*************************



===========
Description
===========



Deregisters an AWS Batch job definition.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/batch-2016-08-10/DeregisterJobDefinition>`_


========
Synopsis
========

::

    deregister-job-definition
  --job-definition <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--job-definition`` (string)


  The name and revision (``name:revision`` ) or full Amazon Resource Name (ARN) of the job definition to deregister. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To deregister a job definition**

This example deregisters a job definition called sleep10.

Command::

  aws batch deregister-job-definition --job-definition sleep10



======
Output
======

