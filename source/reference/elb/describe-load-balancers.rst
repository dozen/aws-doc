[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb describe-load-balancers:


***********************
describe-load-balancers
***********************



===========
Description
===========



Describes the specified the load balancers. If no load balancers are specified, the call describes all of your load balancers.



``describe-load-balancers`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``LoadBalancerDescriptions``


========
Synopsis
========

::

    describe-load-balancers
  [--load-balancer-names <value>]
  [--page-size <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--load-balancer-names`` (list)


  The names of the load balancers.

  



Syntax::

  "string" "string" ...



``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe your load balancers**

This example describes all of your load balancers.

Command::

  aws elb describe-load-balancers

**To describe one of your load balancers**

This example describes the specified load balancer. 

Command::

  aws elb describe-load-balancers --load-balancer-name my-load-balancer

The following example response is for an HTTPS load balancer in a VPC.

Output::

  {
    "LoadBalancerDescriptions": [
      {
        "Subnets": [
            "subnet-15aaab61"
        ],
        "CanonicalHostedZoneNameID": "Z3DZXE0EXAMPLE",
        "CanonicalHostedZoneName": "my-load-balancer-1234567890.us-west-2.elb.amazonaws.com",
        "ListenerDescriptions": [
            {
                "Listener": {
                    "InstancePort": 80,
                    "LoadBalancerPort": 80,
                    "Protocol": "HTTP",
                    "InstanceProtocol": "HTTP"
                },
                "PolicyNames": []
            },
            {
                "Listener": {
                    "InstancePort": 443,
                    "SSLCertificateId": "arn:aws:iam::123456789012:server-certificate/my-server-cert",
                    "LoadBalancerPort": 443,
                    "Protocol": "HTTPS",
                    "InstanceProtocol": "HTTPS"
                },
                "PolicyNames": [
                    "ELBSecurityPolicy-2015-03"
                ]
            }
        ],
        "HealthCheck": {
            "HealthyThreshold": 2,
            "Interval": 30,
            "Target": "HTTP:80/png",
            "Timeout": 3,
            "UnhealthyThreshold": 2
        },
        "VPCId": "vpc-a01106c2",
        "BackendServerDescriptions": [
            {
                "InstancePort": 80,
                "PolicyNames": [
                    "my-ProxyProtocol-policy"
                ]
            }
        ],
        "Instances": [
            {
                "InstanceId": "i-207d9717"
            },
            {
                "InstanceId": "i-afefb49b"
            }
        ],
        "DNSName": "my-load-balancer-1234567890.us-west-2.elb.amazonaws.com",
        "SecurityGroups": [
            "sg-a61988c3"
        ],
        "Policies": {
            "LBCookieStickinessPolicies": [
                {
                    "PolicyName": "my-duration-cookie-policy",
                    "CookieExpirationPeriod": 60
                }
            ],
            "AppCookieStickinessPolicies": [],
            "OtherPolicies": [
                "my-PublicKey-policy",
                "my-authentication-policy",
                "my-SSLNegotiation-policy",
                "my-ProxyProtocol-policy",
                "ELBSecurityPolicy-2015-03"
            ]
        },
        "LoadBalancerName": "my-load-balancer",
        "CreatedTime": "2015-03-19T03:24:02.650Z",
        "AvailabilityZones": [
            "us-west-2a"
        ],
        "Scheme": "internet-facing",
        "SourceSecurityGroup": {
            "OwnerAlias": "123456789012",
            "GroupName": "my-elb-sg"
        }
      }
    ]
  }



======
Output
======

LoadBalancerDescriptions -> (list)

  

  Information about the load balancers.

  

  (structure)

    

    Information about a load balancer.

    

    LoadBalancerName -> (string)

      

      The name of the load balancer.

      

      

    DNSName -> (string)

      

      The external DNS name of the load balancer.

      

      

    CanonicalHostedZoneName -> (string)

      

      The Amazon Route 53 hosted zone associated with the load balancer.

       

      For more information, see `Using Domain Names With Elastic Load Balancing`_ in the *Elastic Load Balancing Developer Guide* .

      

      

    CanonicalHostedZoneNameID -> (string)

      

      The ID of the Amazon Route 53 hosted zone name associated with the load balancer.

      

      

    ListenerDescriptions -> (list)

      

      The listeners for the load balancer.

      

      (structure)

        

        The policies enabled for a listener.

        

        Listener -> (structure)

          

          Information about a listener.

           

          For information about the protocols and the ports supported by Elastic Load Balancing, see `Listener Configurations for Elastic Load Balancing`_ in the *Elastic Load Balancing Developer Guide* .

          

          Protocol -> (string)

            

            The load balancer transport protocol to use for routing: HTTP, HTTPS, TCP, or SSL.

            

            

          LoadBalancerPort -> (integer)

            

            The port on which the load balancer is listening. On EC2-VPC, you can specify any port from the range 1-65535. On EC2-Classic, you can specify any port from the following list: 25, 80, 443, 465, 587, 1024-65535.

            

            

          InstanceProtocol -> (string)

            

            The protocol to use for routing traffic to back-end instances: HTTP, HTTPS, TCP, or SSL.

             

            If the front-end protocol is HTTP, HTTPS, TCP, or SSL, ``InstanceProtocol`` must be at the same protocol.

             

            If there is another listener with the same ``InstancePort`` whose ``InstanceProtocol`` is secure, (HTTPS or SSL), the listener's ``InstanceProtocol`` must also be secure.

             

            If there is another listener with the same ``InstancePort`` whose ``InstanceProtocol`` is HTTP or TCP, the listener's ``InstanceProtocol`` must be HTTP or TCP.

            

            

          InstancePort -> (integer)

            

            The port on which the instance is listening.

            

            

          SSLCertificateId -> (string)

            

            The Amazon Resource Name (ARN) of the server certificate.

            

            

          

        PolicyNames -> (list)

          

          The policies. If there are no policies enabled, the list is empty.

          

          (string)

            

            

          

        

      

    Policies -> (structure)

      

      The policies defined for the load balancer.

      

      AppCookieStickinessPolicies -> (list)

        

        The stickiness policies created using  create-app-cookie-stickiness-policy .

        

        (structure)

          

          Information about a policy for application-controlled session stickiness.

          

          PolicyName -> (string)

            

            The mnemonic name for the policy being created. The name must be unique within a set of policies for this load balancer.

            

            

          CookieName -> (string)

            

            The name of the application cookie used for stickiness.

            

            

          

        

      LBCookieStickinessPolicies -> (list)

        

        The stickiness policies created using  create-lb-cookie-stickiness-policy .

        

        (structure)

          

          Information about a policy for duration-based session stickiness.

          

          PolicyName -> (string)

            

            The name for the policy being created. The name must be unique within the set of policies for this load balancer.

            

            

          CookieExpirationPeriod -> (long)

            

            The time period, in seconds, after which the cookie should be considered stale. If this parameter is not specified, the stickiness session lasts for the duration of the browser session.

            

            

          

        

      OtherPolicies -> (list)

        

        The policies other than the stickiness policies.

        

        (string)

          

          

        

      

    BackendServerDescriptions -> (list)

      

      Information about the back-end servers.

      

      (structure)

        

        Information about the configuration of a back-end server.

        

        InstancePort -> (integer)

          

          The port on which the back-end server is listening.

          

          

        PolicyNames -> (list)

          

          The names of the policies enabled for the back-end server.

          

          (string)

            

            

          

        

      

    AvailabilityZones -> (list)

      

      The Availability Zones for the load balancer.

      

      (string)

        

        

      

    Subnets -> (list)

      

      The IDs of the subnets for the load balancer.

      

      (string)

        

        

      

    VPCId -> (string)

      

      The ID of the VPC for the load balancer.

      

      

    Instances -> (list)

      

      The IDs of the instances for the load balancer.

      

      (structure)

        

        The ID of a back-end instance.

        

        InstanceId -> (string)

          

          The ID of the instance.

          

          

        

      

    HealthCheck -> (structure)

      

      Information about the health checks conducted on the load balancer.

      

      Target -> (string)

        

        The instance being checked. The protocol is either TCP, HTTP, HTTPS, or SSL. The range of valid ports is one (1) through 65535.

         

        TCP is the default, specified as a TCP: port pair, for example "TCP:5000". In this case, a health check simply attempts to open a TCP connection to the instance on the specified port. Failure to connect within the configured timeout is considered unhealthy.

         

        SSL is also specified as SSL: port pair, for example, SSL:5000.

         

        For HTTP/HTTPS, you must include a ping path in the string. HTTP is specified as a HTTP:port;/;PathToPing; grouping, for example "HTTP:80/weather/us/wa/seattle". In this case, a HTTP GET request is issued to the instance on the given port and path. Any answer other than "200 OK" within the timeout period is considered unhealthy.

         

        The total length of the HTTP ping target must be 1024 16-bit Unicode characters or less.

        

        

      Interval -> (integer)

        

        The approximate interval, in seconds, between health checks of an individual instance.

        

        

      Timeout -> (integer)

        

        The amount of time, in seconds, during which no response means a failed health check.

         

        This value must be less than the ``Interval`` value.

        

        

      UnhealthyThreshold -> (integer)

        

        The number of consecutive health check failures required before moving the instance to the ``Unhealthy`` state.

        

        

      HealthyThreshold -> (integer)

        

        The number of consecutive health checks successes required before moving the instance to the ``Healthy`` state.

        

        

      

    SourceSecurityGroup -> (structure)

      

      The security group that you can use as part of your inbound rules for your load balancer's back-end application instances. To only allow traffic from load balancers, add a security group rule to your back end instance that specifies this source security group as the inbound source.

      

      OwnerAlias -> (string)

        

        The owner of the security group.

        

        

      GroupName -> (string)

        

        The name of the security group.

        

        

      

    SecurityGroups -> (list)

      

      The security groups for the load balancer. Valid only for load balancers in a VPC.

      

      (string)

        

        

      

    CreatedTime -> (timestamp)

      

      The date and time the load balancer was created.

      

      

    Scheme -> (string)

      

      The type of load balancer. Valid only for load balancers in a VPC.

       

      If ``Scheme`` is ``internet-facing`` , the load balancer has a public DNS name that resolves to a public IP address.

       

      If ``Scheme`` is ``internal`` , the load balancer has a public DNS name that resolves to a private IP address.

      

      

    

  

NextMarker -> (string)

  

  The marker to use when requesting the next set of results. If there are no additional results, the string is empty.

  

  



.. _Listener Configurations for Elastic Load Balancing: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/elb-listener-config.html
.. _Using Domain Names With Elastic Load Balancing: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/using-domain-names-with-elb.html
