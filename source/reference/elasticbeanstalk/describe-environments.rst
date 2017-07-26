[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk describe-environments:


*********************
describe-environments
*********************



===========
Description
===========



Returns descriptions for existing environments.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/DescribeEnvironments>`_


========
Synopsis
========

::

    describe-environments
  [--application-name <value>]
  [--version-label <value>]
  [--environment-ids <value>]
  [--environment-names <value>]
  [--include-deleted | --no-include-deleted]
  [--included-deleted-back-to <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  If specified, AWS Elastic Beanstalk restricts the returned descriptions to include only those that are associated with this application.

  

``--version-label`` (string)


  If specified, AWS Elastic Beanstalk restricts the returned descriptions to include only those that are associated with this application version.

  

``--environment-ids`` (list)


  If specified, AWS Elastic Beanstalk restricts the returned descriptions to include only those that have the specified IDs.

  



Syntax::

  "string" "string" ...



``--environment-names`` (list)


  If specified, AWS Elastic Beanstalk restricts the returned descriptions to include only those that have the specified names.

  



Syntax::

  "string" "string" ...



``--include-deleted`` | ``--no-include-deleted`` (boolean)


  Indicates whether to include deleted environments:

   

   ``true`` : Environments that have been deleted after ``IncludedDeletedBackTo`` are displayed.

   

   ``false`` : Do not include deleted environments.

  

``--included-deleted-back-to`` (timestamp)


  If specified when ``include-deleted`` is set to ``true`` , then environments deleted after this date are displayed. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To view information about an environment**

The following command retrieves information about an environment named ``my-env``::

  aws elasticbeanstalk describe-environments --environment-names my-env

Output::

  {
      "Environments": [
          {
              "ApplicationName": "my-app",
              "EnvironmentName": "my-env",
              "VersionLabel": "7f58-stage-150812_025409",
              "Status": "Ready",
              "EnvironmentId": "e-rpqsewtp2j",
              "EndpointURL": "awseb-e-w-AWSEBLoa-1483140XB0Q4L-109QXY8121.us-west-2.elb.amazonaws.com",
              "SolutionStackName": "64bit Amazon Linux 2015.03 v2.0.0 running Tomcat 8 Java 8",
              "CNAME": "my-env.elasticbeanstalk.com",
              "Health": "Green",
              "AbortableOperationInProgress": false,
              "Tier": {
                  "Version": " ",
                  "Type": "Standard",
                  "Name": "WebServer"
              },
              "DateUpdated": "2015-08-12T18:16:55.019Z",
              "DateCreated": "2015-08-07T20:48:49.599Z"
          }
      ]
  }


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

      

      

    PlatformArn -> (string)

      

      The ARN of the custom platform.

      

      

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

      

      Returns the health status of the application running in your environment. For more information, see `Health Colors and Statuses <http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/health-enhanced-status.html>`_ .

      

      

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

        

        A link to another environment, defined in the environment's manifest. Links provide connection information in system properties that can be used to connect to another environment in the same group. See `Environment Manifest (env.yaml) <http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/environment-cfg-manifest.html>`_ for details.

        

        LinkName -> (string)

          

          The name of the link.

          

          

        EnvironmentName -> (string)

          

          The name of the linked environment (the dependency).

          

          

        

      

    

  

