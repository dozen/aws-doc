[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb describe-load-balancer-attributes:


*********************************
describe-load-balancer-attributes
*********************************



===========
Description
===========



Describes the attributes for the specified load balancer.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticloadbalancing-2012-06-01/DescribeLoadBalancerAttributes>`_


========
Synopsis
========

::

    describe-load-balancer-attributes
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

**To describe the attributes of a load balancer**

This example describes the attributes of the specified load balancer.

Command::

  aws elb describe-load-balancer-attributes --load-balancer-name my-load-balancer

Output::

  {
    "LoadBalancerAttributes": {
        "ConnectionDraining": {
            "Enabled": false,
            "Timeout": 300
        },
        "CrossZoneLoadBalancing": {
            "Enabled": true
        },
        "ConnectionSettings": {
            "IdleTimeout": 30
        },
        "AccessLog": {
            "Enabled": false
      }
    }
  }



======
Output
======

LoadBalancerAttributes -> (structure)

  

  Information about the load balancer attributes.

  

  CrossZoneLoadBalancing -> (structure)

    

    If enabled, the load balancer routes the request traffic evenly across all instances regardless of the Availability Zones.

     

    For more information, see `Configure Cross-Zone Load Balancing <http://docs.aws.amazon.com/elasticloadbalancing/latest/classic/enable-disable-crosszone-lb.html>`_ in the *Classic Load Balancer Guide* .

    

    Enabled -> (boolean)

      

      Specifies whether cross-zone load balancing is enabled for the load balancer.

      

      

    

  AccessLog -> (structure)

    

    If enabled, the load balancer captures detailed information of all requests and delivers the information to the Amazon S3 bucket that you specify.

     

    For more information, see `Enable Access Logs <http://docs.aws.amazon.com/elasticloadbalancing/latest/classic/enable-access-logs.html>`_ in the *Classic Load Balancer Guide* .

    

    Enabled -> (boolean)

      

      Specifies whether access logs are enabled for the load balancer.

      

      

    S3BucketName -> (string)

      

      The name of the Amazon S3 bucket where the access logs are stored.

      

      

    EmitInterval -> (integer)

      

      The interval for publishing the access logs. You can specify an interval of either 5 minutes or 60 minutes.

       

      Default: 60 minutes

      

      

    S3BucketPrefix -> (string)

      

      The logical hierarchy you created for your Amazon S3 bucket, for example ``my-bucket-prefix/prod`` . If the prefix is not provided, the log is placed at the root level of the bucket.

      

      

    

  ConnectionDraining -> (structure)

    

    If enabled, the load balancer allows existing requests to complete before the load balancer shifts traffic away from a deregistered or unhealthy instance.

     

    For more information, see `Configure Connection Draining <http://docs.aws.amazon.com/elasticloadbalancing/latest/classic/config-conn-drain.html>`_ in the *Classic Load Balancer Guide* .

    

    Enabled -> (boolean)

      

      Specifies whether connection draining is enabled for the load balancer.

      

      

    Timeout -> (integer)

      

      The maximum time, in seconds, to keep the existing connections open before deregistering the instances.

      

      

    

  ConnectionSettings -> (structure)

    

    If enabled, the load balancer allows the connections to remain idle (no data is sent over the connection) for the specified duration.

     

    By default, Elastic Load Balancing maintains a 60-second idle connection timeout for both front-end and back-end connections of your load balancer. For more information, see `Configure Idle Connection Timeout <http://docs.aws.amazon.com/elasticloadbalancing/latest/classic/config-idle-timeout.html>`_ in the *Classic Load Balancer Guide* .

    

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

        

        

      

    

  

