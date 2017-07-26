[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 create-traffic-policy:


*********************
create-traffic-policy
*********************



===========
Description
===========



Creates a traffic policy, which you use to create multiple DNS resource record sets for one domain name (such as example.com) or one subdomain name (such as www.example.com).

 

To create a traffic policy, send a ``POST`` request to the ``/*Route 53 API version* /trafficpolicy`` resource. The request body must include a document with a ``CreateTrafficPolicyRequest`` element. The response includes the ``CreateTrafficPolicyResponse`` element, which contains information about the new traffic policy.



========
Synopsis
========

::

    create-traffic-policy
  --name <value>
  --document <value>
  [--comment <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--name`` (string)


  The name of the traffic policy.

  

``--document`` (string)


  The definition of this traffic policy in JSON format.

  

``--comment`` (string)


  Any comments that you want to include about the traffic policy.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

TrafficPolicy -> (structure)

  

  A complex type that contains settings for the new traffic policy.

  

  Id -> (string)

    

    

  Version -> (integer)

    

    

  Name -> (string)

    

    

  Type -> (string)

    

    

  Document -> (string)

    

    

  Comment -> (string)

    

    

  

Location -> (string)

  

  

