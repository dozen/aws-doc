[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk compose-environments:


********************
compose-environments
********************



===========
Description
===========



Create or update a group of environments that each run a separate component of a single application. Takes a list of version labels that specify application source bundles for each of the environments to create or update. The name of each environment and other required information must be included in the source bundles in an environment manifest named ``env.yaml`` . See `Compose Environments`_ for details.



========
Synopsis
========

::

    compose-environments
  [--application-name <value>]
  [--group-name <value>]
  [--version-labels <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--application-name`` (string)


  The name of the application to which the specified source bundles belong.

  

``--group-name`` (string)


  The name of the group to which the target environments belong. Specify a group name only if the environment name defined in each target environment's manifest ends with a + (plus) character. See `Environment Manifest (env.yaml)`_ for details.

  

``--version-labels`` (list)


  A list of version labels, specifying one or more application source bundles that belong to the target application. Each source bundle must include an environment manifest that specifies the name of the environment and the name of the solution stack to use, and optionally can specify environment links to create.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Environments -> (list)

  

  Returns an  EnvironmentDescription list. 

  

  (structure)

    

    Describes the properties of an environment.

    

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
.. _Compose Environments: http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/environment-mgmt-compose.html
.. _Health Colors and Statuses: http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/health-enhanced-status.html
