[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 delete-traffic-policy:


*********************
delete-traffic-policy
*********************



===========
Description
===========



Deletes a traffic policy. To delete a traffic policy, send a ``DELETE`` request to the ``/*Route 53 API version* /trafficpolicy`` resource.



========
Synopsis
========

::

    delete-traffic-policy
  --id <value>
  --traffic-policy-version <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--id`` (string)


  The ID of the traffic policy that you want to delete.

  

``--traffic-policy-version`` (integer)


  The version number of the traffic policy that you want to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

