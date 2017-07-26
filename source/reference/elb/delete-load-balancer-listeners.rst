[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb delete-load-balancer-listeners:


******************************
delete-load-balancer-listeners
******************************



===========
Description
===========



Deletes the specified listeners from the specified load balancer.



========
Synopsis
========

::

    delete-load-balancer-listeners
  --load-balancer-name <value>
  --load-balancer-ports <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

