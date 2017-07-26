[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb delete-load-balancer:


********************
delete-load-balancer
********************



===========
Description
===========



Deletes the specified load balancer.

 

If you are attempting to recreate a load balancer, you must reconfigure all settings. The DNS name associated with a deleted load balancer are no longer usable. The name and associated DNS record of the deleted load balancer no longer exist and traffic sent to any of its IP addresses is no longer delivered to your instances.

 

If the load balancer does not exist or has already been deleted, the call to ``delete-load-balancer`` still succeeds.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancing-2012-06-01/DeleteLoadBalancer>`_


========
Synopsis
========

::

    delete-load-balancer
  --load-balancer-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--load-balancer-name`` (string)


  The name of the load balancer.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

