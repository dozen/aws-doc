[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb register-instances-with-load-balancer:


*************************************
register-instances-with-load-balancer
*************************************



===========
Description
===========



Adds the specified instances to the specified load balancer.

 

The instance must be a running instance in the same network as the load balancer (EC2-Classic or the same VPC). If you have EC2-Classic instances and a load balancer in a VPC with ClassicLink enabled, you can link the EC2-Classic instances to that VPC and then register the linked EC2-Classic instances with the load balancer in the VPC.

 

Note that ``RegisterInstanceWithLoadBalancer`` completes when the request has been registered. Instance registration takes a little time to complete. To check the state of the registered instances, use  describe-load-balancers or  describe-instance-health .

 

After the instance is registered, it starts receiving traffic and requests from the load balancer. Any instance that is not in one of the Availability Zones registered for the load balancer is moved to the ``OutOfService`` state. If an Availability Zone is added to the load balancer later, any instances registered with the load balancer move to the ``InService`` state.

 

If you stop an instance registered with a load balancer and then start it, the IP addresses associated with the instance changes. Elastic Load Balancing cannot recognize the new IP address, which prevents it from routing traffic to the instances. We recommend that you use the following sequence: stop the instance, deregister the instance, start the instance, and then register the instance. To deregister instances from a load balancer, use  deregister-instances-from-load-balancer .

 

For more information, see `Deregister and Register EC2 instances`_ in the *Elastic Load Balancing Developer Guide* .



========
Synopsis
========

::

    register-instances-with-load-balancer
  --load-balancer-name <value>
  --instances <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--load-balancer-name`` (string)


  The name of the load balancer.

  

``--instances`` (list)


  The IDs of the instances.

  



Shorthand Syntax::

    --instances InstanceId1 InstanceId2 InstanceId3




JSON Syntax::

  [
    {
      "InstanceId": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To register instances with a load balancer**

This example registers the specified instance with the specified load balancer.

Command::

  aws elb register-instances-with-load-balancer --load-balancer-name my-load-balancer --instances i-d6f6fae3

Output::

   {
      "Instances": [
          {
              "InstanceId": "i-d6f6fae3"
          },
          {
              "InstanceId": "i-207d9717"
          },
          {
              "InstanceId": "i-afefb49b"
          }
      ]
   }



======
Output
======

Instances -> (list)

  

  The updated list of instances for the load balancer.

  

  (structure)

    

    The ID of a back-end instance.

    

    InstanceId -> (string)

      

      The ID of the instance.

      

      

    

  



.. _Deregister and Register EC2 instances: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/US_DeReg_Reg_Instances.html
