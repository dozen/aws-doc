[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb disable-availability-zones-for-load-balancer:


********************************************
disable-availability-zones-for-load-balancer
********************************************



===========
Description
===========



Removes the specified Availability Zones from the set of Availability Zones for the specified load balancer.

 

There must be at least one Availability Zone registered with a load balancer at all times. After an Availability Zone is removed, all instances registered with the load balancer that are in the removed Availability Zone go into the ``OutOfService`` state. Then, the load balancer attempts to equally balance the traffic among its remaining Availability Zones.

 

For more information, see `Disable an Availability Zone from a Load-Balanced Application`_ in the *Elastic Load Balancing Developer Guide* .



========
Synopsis
========

::

    disable-availability-zones-for-load-balancer
  --load-balancer-name <value>
  --availability-zones <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--load-balancer-name`` (string)


  The name of the load balancer.

  

``--availability-zones`` (list)


  The Availability Zones.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To disable Availability Zones for a load balancer**

This example removes the specified Availability Zone from the set of Availability Zones for the specified load balancer.
 
Command::

    aws elb disable-availability-zones-for-load-balancer --load-balancer-name my-load-balancer --availability-zones us-west-2a

Output::

    {
        "AvailabilityZones": [
            "us-west-2b"
        ]
    }


======
Output
======

AvailabilityZones -> (list)

  

  The remaining Availability Zones for the load balancer.

  

  (string)

    

    

  



.. _Disable an Availability Zone from a Load-Balanced Application: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/US_ShrinkLBApp04.html
