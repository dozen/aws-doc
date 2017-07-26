[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 update-traffic-policy-comment:


*****************************
update-traffic-policy-comment
*****************************



===========
Description
===========



Updates the comment for a specified traffic policy version.

 

To update the comment, send a ``POST`` request to the ``/*Route 53 API version* /trafficpolicy/`` resource.

 

The request body must include a document with an ``UpdateTrafficPolicyCommentRequest`` element.



========
Synopsis
========

::

    update-traffic-policy-comment
  --id <value>
  --comment <value>
  --traffic-policy-version <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--id`` (string)


  The value of ``Id`` for the traffic policy for which you want to update the comment.

  

``--comment`` (string)


  The new comment for the specified traffic policy and version.

  

``--traffic-policy-version`` (integer)


  The value of ``Version`` for the traffic policy for which you want to update the comment.

  

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

    

    

  

