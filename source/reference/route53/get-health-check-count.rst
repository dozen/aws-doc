[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 get-health-check-count:


**********************
get-health-check-count
**********************



===========
Description
===========



To retrieve a count of all your health checks, send a ``GET`` request to the ``/*Route 53 API version* /healthcheckcount`` resource.



========
Synopsis
========

::

    get-health-check-count
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

HealthCheckCount -> (long)

  

  The number of health checks associated with the current AWS account.

  

  

