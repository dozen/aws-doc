[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb modify-load-balancer-attributes:


*******************************
modify-load-balancer-attributes
*******************************



===========
Description
===========



Modifies the attributes of the specified load balancer.

 

You can modify the load balancer attributes, such as ``AccessLogs`` , ``ConnectionDraining`` , and ``CrossZoneLoadBalancing`` by either enabling or disabling them. Or, you can modify the load balancer attribute ``ConnectionSettings`` by specifying an idle connection timeout value for your load balancer.

 

For more information, see the following in the *Elastic Load Balancing Developer Guide* :

 

 
* `Cross-Zone Load Balancing`_ 
 
* `Connection Draining`_ 
 
* `Access Logs`_ 
 
* `Idle Connection Timeout`_ 
 



========
Synopsis
========

::

    modify-load-balancer-attributes
  --load-balancer-name <value>
  --load-balancer-attributes <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--load-balancer-name`` (string)


  The name of the load balancer.

  

``--load-balancer-attributes`` (structure)


  The attributes of the load balancer.

  



Shorthand Syntax::

    CrossZoneLoadBalancing={Enabled=boolean},AccessLog={Enabled=boolean,S3BucketName=string,EmitInterval=integer,S3BucketPrefix=string},ConnectionDraining={Enabled=boolean,Timeout=integer},ConnectionSettings={IdleTimeout=integer},AdditionalAttributes=[{Key=string,Value=string},{Key=string,Value=string}]




JSON Syntax::

  {
    "CrossZoneLoadBalancing": {
      "Enabled": true|false
    },
    "AccessLog": {
      "Enabled": true|false,
      "S3BucketName": "string",
      "EmitInterval": integer,
      "S3BucketPrefix": "string"
    },
    "ConnectionDraining": {
      "Enabled": true|false,
      "Timeout": integer
    },
    "ConnectionSettings": {
      "IdleTimeout": integer
    },
    "AdditionalAttributes": [
      {
        "Key": "string",
        "Value": "string"
      }
      ...
    ]
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To modify the attributes of a load balancer**

This example modifies the ``CrossZoneLoadBalancing`` attribute of the specified load balancer.

Command::

    aws elb modify-load-balancer-attributes --load-balancer-name my-load-balancer --load-balancer-attributes "{\"CrossZoneLoadBalancing\":{\"Enabled\":true}}"

Output::

  {
      "LoadBalancerAttributes": {
          "CrossZoneLoadBalancing": {
              "Enabled": true
          }
      },
      "LoadBalancerName": "my-load-balancer"
  }

This example modifies the ``ConnectionDraining`` attribute of the specified load balancer.

Command::

    aws elb modify-load-balancer-attributes --load-balancer-name my-load-balancer --load-balancer-attributes "{\"ConnectionDraining\":{\"Enabled\":true,\"Timeout\":300}}"

Output::

  {
      "LoadBalancerAttributes": {
          "ConnectionDraining": {
              "Enabled": true,
              "Timeout": 300
          }
      },
      "LoadBalancerName": "my-load-balancer"
  }


======
Output
======

LoadBalancerName -> (string)

  

  The name of the load balancer.

  

  

LoadBalancerAttributes -> (structure)

  

  The attributes for a load balancer.

  

  CrossZoneLoadBalancing -> (structure)

    

    If enabled, the load balancer routes the request traffic evenly across all back-end instances regardless of the Availability Zones.

     

    For more information, see `Enable Cross-Zone Load Balancing`_ in the *Elastic Load Balancing Developer Guide* .

    

    Enabled -> (boolean)

      

      Specifies whether cross-zone load balancing is enabled for the load balancer.

      

      

    

  AccessLog -> (structure)

    

    If enabled, the load balancer captures detailed information of all requests and delivers the information to the Amazon S3 bucket that you specify.

     

    For more information, see `Enable Access Logs`_ in the *Elastic Load Balancing Developer Guide* .

    

    Enabled -> (boolean)

      

      Specifies whether access log is enabled for the load balancer.

      

      

    S3BucketName -> (string)

      

      The name of the Amazon S3 bucket where the access logs are stored.

      

      

    EmitInterval -> (integer)

      

      The interval for publishing the access logs. You can specify an interval of either 5 minutes or 60 minutes.

       

      Default: 60 minutes

      

      

    S3BucketPrefix -> (string)

      

      The logical hierarchy you created for your Amazon S3 bucket, for example ``my-bucket-prefix/prod`` . If the prefix is not provided, the log is placed at the root level of the bucket.

      

      

    

  ConnectionDraining -> (structure)

    

    If enabled, the load balancer allows existing requests to complete before the load balancer shifts traffic away from a deregistered or unhealthy back-end instance.

     

    For more information, see `Enable Connection Draining`_ in the *Elastic Load Balancing Developer Guide* .

    

    Enabled -> (boolean)

      

      Specifies whether connection draining is enabled for the load balancer.

      

      

    Timeout -> (integer)

      

      The maximum time, in seconds, to keep the existing connections open before deregistering the instances.

      

      

    

  ConnectionSettings -> (structure)

    

    If enabled, the load balancer allows the connections to remain idle (no data is sent over the connection) for the specified duration.

     

    By default, Elastic Load Balancing maintains a 60-second idle connection timeout for both front-end and back-end connections of your load balancer. For more information, see `Configure Idle Connection Timeout`_ in the *Elastic Load Balancing Developer Guide* .

    

    IdleTimeout -> (integer)

      

      The time, in seconds, that the connection is allowed to be idle (no data has been sent over the connection) before it is closed by the load balancer.

      

      

    

  AdditionalAttributes -> (list)

    

    This parameter is reserved.

    

    (structure)

      

      This data type is reserved.

      

      Key -> (string)

        

        This parameter is reserved.

        

        

      Value -> (string)

        

        This parameter is reserved.

        

        

      

    

  



.. _Access Logs: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/access-log-collection.html
.. _Cross-Zone Load Balancing: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/TerminologyandKeyConcepts.html#request-routing
.. _Enable Cross-Zone Load Balancing: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/enable-disable-crosszone-lb.html
.. _Enable Connection Draining: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/config-conn-drain.html
.. _Connection Draining: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/TerminologyandKeyConcepts.html#conn-drain
.. _Enable Access Logs: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/enable-access-logs.html
.. _Configure Idle Connection Timeout: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/config-idle-timeout.html
.. _Idle Connection Timeout: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/TerminologyandKeyConcepts.html#idle-timeout
