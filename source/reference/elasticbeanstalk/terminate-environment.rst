[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk terminate-environment:


*********************
terminate-environment
*********************



===========
Description
===========



Terminates the specified environment. 



========
Synopsis
========

::

    terminate-environment
  [--environment-id <value>]
  [--environment-name <value>]
  [--terminate-resources | --no-terminate-resources]
  [--force-terminate | --no-force-terminate]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--environment-id`` (string)


  The ID of the environment to terminate.

   

  Condition: You must specify either this or an EnvironmentName, or both. If you do not specify either, AWS Elastic Beanstalk returns ``MissingRequiredParameter`` error. 

  

``--environment-name`` (string)


  The name of the environment to terminate.

   

  Condition: You must specify either this or an EnvironmentId, or both. If you do not specify either, AWS Elastic Beanstalk returns ``MissingRequiredParameter`` error. 

  

``--terminate-resources`` | ``--no-terminate-resources`` (boolean)


  Indicates whether the associated AWS resources should shut down when the environment is terminated: 

   

   
  * ``true`` : The specified environment as well as the associated AWS resources, such as Auto Scaling group and LoadBalancer, are terminated. 
   
  * ``false`` : AWS Elastic Beanstalk resource management is removed from the environment, but the AWS resources continue to operate. 
   

   

  For more information, see the `AWS Elastic Beanstalk User Guide.`_  

   

  Default: ``true``  

   

  Valid Values: ``true`` | ``false``  

  

``--force-terminate`` | ``--no-force-terminate`` (boolean)


  Terminates the target environment even if another environment in the same group is dependent on it.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To terminate an environment**

The following command terminates an Elastic Beanstalk environment named ``my-env``::

  aws elasticbeanstalk terminate-environment --environment-name my-env

Output::

  {
      "ApplicationName": "my-app",
      "EnvironmentName": "my-env",
      "Status": "Terminating",
      "EnvironmentId": "e-fh2eravpns",
      "EndpointURL": "awseb-e-f-AWSEBLoa-1I9XUMP4-8492WNUP202574.us-west-2.elb.amazonaws.com",
      "SolutionStackName": "64bit Amazon Linux 2015.03 v2.0.0 running Tomcat 8 Java 8",
      "CNAME": "my-env.elasticbeanstalk.com",
      "Health": "Grey",
      "AbortableOperationInProgress": false,
      "Tier": {
          "Version": " ",
          "Type": "Standard",
          "Name": "WebServer"
      },
      "DateUpdated": "2015-08-12T19:05:54.744Z",
      "DateCreated": "2015-08-12T18:52:53.622Z"
  }


======
Output
======

EnvironmentName -> (string)

  

  The name of this environment.

  

  

EnvironmentId -> (string)

  

  The ID of this environment. 

  

  

ApplicationName -> (string)

  

  The name of the application associated with this environment.

  

  

VersionLabel -> (string)

  

  The application version deployed in this environment.

  

  

SolutionStackName -> (string)

  

  The name of the ``SolutionStack`` deployed with this environment. 

  

  

TemplateName -> (string)

  

  The name of the configuration template used to originally launch this environment. 

  

  

Description -> (string)

  

  Describes this environment.

  

  

EndpointURL -> (string)

  

  For load-balanced, autoscaling environments, the URL to the LoadBalancer. For single-instance environments, the IP address of the instance.

  

  

CNAME -> (string)

  

  The URL to the CNAME for this environment. 

  

  

DateCreated -> (timestamp)

  

  The creation date for this environment.

  

  

DateUpdated -> (timestamp)

  

  The last modified date for this environment.

  

  

Status -> (string)

  

  The current operational status of the environment: 

   

   
  * ``Launching`` : Environment is in the process of initial deployment. 
   
  * ``Updating`` : Environment is in the process of updating its configuration settings or application version. 
   
  * ``Ready`` : Environment is available to have an action performed on it, such as update or terminate. 
   
  * ``Terminating`` : Environment is in the shut-down process. 
   
  * ``Terminated`` : Environment is not running. 
   

  

  

AbortableOperationInProgress -> (boolean)

  

  Indicates if there is an in-progress environment configuration update or application version deployment that you can cancel.

   

   ``true:`` There is an update in progress. 

   

   ``false:`` There are no updates currently in progress. 

  

  

Health -> (string)

  

  Describes the health status of the environment. AWS Elastic Beanstalk indicates the failure levels for a running environment: 

   

   
  * ``Red`` : Indicates the environment is not responsive. Occurs when three or more consecutive failures occur for an environment. 
   
  * ``Yellow`` : Indicates that something is wrong. Occurs when two consecutive failures occur for an environment. 
   
  * ``Green`` : Indicates the environment is healthy and fully functional. 
   
  * ``Grey`` : Default health for a new environment. The environment is not fully launched and health checks have not started or health checks are suspended during an ``update-environment`` or ``RestartEnvironement`` request. 
   

   

  Default: ``Grey``  

  

  

HealthStatus -> (string)

  

  Returns the health status of the application running in your environment. For more information, see `Health Colors and Statuses`_ .

  

  

Resources -> (structure)

  

  The description of the AWS resources used by this environment.

  

  LoadBalancer -> (structure)

    

    Describes the LoadBalancer.

    

    LoadBalancerName -> (string)

      

      The name of the LoadBalancer.

      

      

    Domain -> (string)

      

      The domain name of the LoadBalancer.

      

      

    Listeners -> (list)

      

      A list of Listeners used by the LoadBalancer.

      

      (structure)

        

        Describes the properties of a Listener for the LoadBalancer.

        

        Protocol -> (string)

          

          The protocol that is used by the Listener.

          

          

        Port -> (integer)

          

          The port that is used by the Listener.

          

          

        

      

    

  

Tier -> (structure)

  

  Describes the current tier of this environment.

  

  Name -> (string)

    

    The name of this environment tier.

    

    

  Type -> (string)

    

    The type of this environment tier.

    

    

  Version -> (string)

    

    The version of this environment tier.

    

    

  

EnvironmentLinks -> (list)

  

  A list of links to other environments in the same group.

  

  (structure)

    

    A link to another environment, defined in the environment's manifest. Links provide connection information in system properties that can be used to connect to another environment in the same group. See `Environment Manifest (env.yaml)`_ for details.

    

    LinkName -> (string)

      

      The name of the link.

      

      

    EnvironmentName -> (string)

      

      The name of the linked environment (the dependency).

      

      

    

  



.. _Environment Manifest (env.yaml): http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/environment-mgmt-compose.html#environment-mgmt-compose-envyaml
.. _AWS Elastic Beanstalk User Guide.: http://docs.aws.amazon.com/elasticbeanstalk/latest/ug/
.. _Health Colors and Statuses: http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/health-enhanced-status.html
