[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb delete-load-balancer:


********************
delete-load-balancer
********************



===========
Description
===========



Deletes the specified load balancer.

 

If you are attempting to recreate a load balancer, you must reconfigure all settings. The DNS name associated with a deleted load balancer are no longer usable. The name and associated DNS record of the deleted load balancer no longer exist and traffic sent to any of its IP addresses is no longer delivered to back-end instances.

 

If the load balancer does not exist or has already been deleted, the call to ``delete-load-balancer`` still succeeds.



========
Synopsis
========

::

    delete-load-balancer
  --load-balancer-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--load-balancer-name`` (string)


  The name of the load balancer.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a load balancer**

This example deletes the specified load balancer.

Command::

      aws elb delete-load-balancer --load-balancer-name my-load-balancer


======
Output
======

