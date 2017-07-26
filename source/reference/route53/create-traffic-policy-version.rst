[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 create-traffic-policy-version:


*****************************
create-traffic-policy-version
*****************************



===========
Description
===========



Creates a new version of an existing traffic policy. When you create a new version of a traffic policy, you specify the ID of the traffic policy that you want to update and a JSON-formatted document that describes the new version.

 

You use traffic policies to create multiple DNS resource record sets for one domain name (such as example.com) or one subdomain name (such as www.example.com).

 

To create a new version, send a ``POST`` request to the ``/*Route 53 API version* /trafficpolicy/`` resource. The request body includes a document with a ``CreateTrafficPolicyVersionRequest`` element. The response returns the ``CreateTrafficPolicyVersionResponse`` element, which contains information about the new version of the traffic policy.



========
Synopsis
========

::

    create-traffic-policy-version
  --id <value>
  --document <value>
  [--comment <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--id`` (string)


  The ID of the traffic policy for which you want to create a new version.

  

``--document`` (string)


  The definition of a new traffic policy version, in JSON format. You must specify the full definition of the new traffic policy. You cannot specify just the differences between the new version and a previous version.

  

``--comment`` (string)


  Any comments that you want to include about the new traffic policy version.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

TrafficPolicy -> (structure)

  

  A complex type that contains settings for the new version of the traffic policy.

  

  Id -> (string)

    

    

  Version -> (integer)

    

    

  Name -> (string)

    

    

  Type -> (string)

    

    

  Document -> (string)

    

    

  Comment -> (string)

    

    

  

Location -> (string)

  

  

