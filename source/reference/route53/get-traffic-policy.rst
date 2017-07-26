[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 get-traffic-policy:


******************
get-traffic-policy
******************



===========
Description
===========



Gets information about a specific traffic policy version. To get the information, send a ``GET`` request to the ``/*Route 53 API version* /trafficpolicy`` resource.



========
Synopsis
========

::

    get-traffic-policy
  --id <value>
  --traffic-policy-version <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--id`` (string)


  The ID of the traffic policy that you want to get information about.

  

``--traffic-policy-version`` (integer)


  The version number of the traffic policy that you want to get information about.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

TrafficPolicy -> (structure)

  

  A complex type that contains settings for the specified traffic policy.

  

  Id -> (string)

    

    

  Version -> (integer)

    

    

  Name -> (string)

    

    

  Type -> (string)

    

    

  Document -> (string)

    

    

  Comment -> (string)

    

    

  

