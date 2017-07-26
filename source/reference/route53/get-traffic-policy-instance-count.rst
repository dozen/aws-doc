[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 get-traffic-policy-instance-count:


*********************************
get-traffic-policy-instance-count
*********************************



===========
Description
===========



Gets the number of traffic policy instances that are associated with the current AWS account.

 

To get the number of traffic policy instances, send a ``GET`` request to the ``/*Route 53 API version* /trafficpolicyinstancecount`` resource.



========
Synopsis
========

::

    get-traffic-policy-instance-count
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

TrafficPolicyInstanceCount -> (integer)

  

  The number of traffic policy instances that are associated with the current AWS account.

  

  

