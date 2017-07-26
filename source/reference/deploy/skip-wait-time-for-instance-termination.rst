[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy skip-wait-time-for-instance-termination:


***************************************
skip-wait-time-for-instance-termination
***************************************



===========
Description
===========



In a blue/green deployment, overrides any specified wait time and starts terminating instances immediately after the traffic routing is completed.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/SkipWaitTimeForInstanceTermination>`_


========
Synopsis
========

::

    skip-wait-time-for-instance-termination
  [--deployment-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--deployment-id`` (string)


  The ID of the blue/green deployment for which you want to skip the instance termination wait time.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None