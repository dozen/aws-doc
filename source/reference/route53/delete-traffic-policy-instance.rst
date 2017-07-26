[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 delete-traffic-policy-instance:


******************************
delete-traffic-policy-instance
******************************



===========
Description
===========



Deletes a traffic policy instance and all of the resource record sets that Amazon Route 53 created when you created the instance.

 

To delete a traffic policy instance, send a ``DELETE`` request to the ``/*Route 53 API version* /trafficpolicy/*traffic policy instance ID*`` resource.

 

.. warning::

  When you delete a traffic policy instance, Amazon Route 53 also deletes all of the resource record sets that were created when you created the traffic policy instance.



========
Synopsis
========

::

    delete-traffic-policy-instance
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--id`` (string)


  The ID of the traffic policy instance that you want to delete. 

   

  .. warning::

    When you delete a traffic policy instance, Amazon Route 53 also deletes all of the resource record sets that were created when you created the traffic policy instance.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

