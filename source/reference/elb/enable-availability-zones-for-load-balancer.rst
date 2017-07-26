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

 

For more information, see `Add or Remove Availability Zones <http://docs.aws.amazon.com/elasticloadbalancing/latest/classic/enable-disable-az.html>`_ in the *Classic Load Balancer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancing-2012-06-01/EnableAvailabilityZonesForLoadBalancer>`_


========
Synopsis
========

::

    enable-availability-zones-for-load-balancer
  --load-balancer-name <value>
  --availability-zones <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

    

    

  

