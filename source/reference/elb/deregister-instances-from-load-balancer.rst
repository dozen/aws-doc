[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb deregister-instances-from-load-balancer:


***************************************
deregister-instances-from-load-balancer
***************************************



===========
Description
===========



Deregisters the specified instances from the specified load balancer. After the instance is deregistered, it no longer receives traffic from the load balancer.

 

You can use  describe-load-balancers to verify that the instance is deregistered from the load balancer.

 

For more information, see `Deregister and Register Amazon EC2 instances`_ in the *Elastic Load Balancing Developer Guide* .



========
Synopsis
========

::

    deregister-instances-from-load-balancer
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

**To deregister instances from a load balancer**

This example deregisters the specified instance from the specified load balancer.

Command::

      aws elb deregister-instances-from-load-balancer --load-balancer-name my-load-balancer --instances i-d6f6fae3


Output::

    {
        "Instances": [
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

  

  The remaining instances registered with the load balancer.

  

  (structure)

    

    The ID of a back-end instance.

    

    InstanceId -> (string)

      

      The ID of the instance.

      

      

    

  



.. _Deregister and Register Amazon EC2 instances: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/US_DeReg_Reg_Instances.html
