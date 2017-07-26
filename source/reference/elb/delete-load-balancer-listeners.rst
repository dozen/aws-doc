[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb delete-load-balancer-listeners:


******************************
delete-load-balancer-listeners
******************************



===========
Description
===========



Deletes the specified listeners from the specified load balancer.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancing-2012-06-01/DeleteLoadBalancerListeners>`_


========
Synopsis
========

::

    delete-load-balancer-listeners
  --load-balancer-name <value>
  --load-balancer-ports <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--load-balancer-name`` (string)


  The name of the load balancer.

  

``--load-balancer-ports`` (list)


  The client port numbers of the listeners.

  



Syntax::

  integer integer ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a listener from your load balancer**

This example deletes the listener for the specified port from the specified load balancer.

Command::

      aws elb delete-load-balancer-listeners --load-balancer-name my-load-balancer --load-balancer-ports 80


======
Output
======

