[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` . :ref:`wait <cli:aws ecs wait>` ]

.. _cli:aws ecs wait services-stable:


***************
services-stable
***************



===========
Description
===========

Wait until JMESPath query services | [@[?length(deployments)!=`1`], @[?desiredCount!=runningCount]][] | length(@) == `0` returns True when polling with ``describe-services``. It will poll every 15 seconds until a successful state has been reached. This will exit with a return code of 255 after 40 failed checks.

========
Synopsis
========

::

    services-stable
  [--cluster <value>]
  --services <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cluster`` (string)


  The name of the cluster that hosts the service to describe. If you do not specify a cluster, the default cluster is assumed.

  

``--services`` (list)


  A list of services to describe.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None