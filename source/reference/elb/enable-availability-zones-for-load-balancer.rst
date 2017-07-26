[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb enable-availability-zones-for-load-balancer:


*******************************************
enable-availability-zones-for-load-balancer
*******************************************



===========
Description
===========



Adds the specified Availability Zones to the set of Availability Zones for the specified load balancer.

 

The load balancer evenly distributes requests across all its registered Availability Zones that contain instances.

 

For more information, see `Add Availability Zone`_ in the *Elastic Load Balancing Developer Guide* .



========
Synopsis
========

::

    enable-availability-zones-for-load-balancer
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


  The Availability Zones. These must be in the same region as the load balancer.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To enable Availability Zones for a load balancer**

This example adds the specified Availability Zone to the specified load balancer.

Command::

    aws elb enable-availability-zones-for-load-balancer --load-balancer-name my-load-balancer --availability-zones us-west-2b

Output::

    {
        "AvailabilityZones": [
            "us-west-2a",
            "us-west-2b"
        ]
    }



======
Output
======

AvailabilityZones -> (list)

  

  The updated list of Availability Zones for the load balancer.

  

  (string)

    

    

  



.. _Add Availability Zone: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/US_AddLBAvailabilityZone.html
