[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk update-environment:


******************
update-environment
******************



===========
Description
===========



Updates the environment description, deploys a new application version, updates the configuration settings to an entirely new configuration template, or updates select configuration option values in the running environment. 

 

Attempting to update both the release and configuration is not allowed and AWS Elastic Beanstalk returns an ``InvalidParameterCombination`` error. 

 

When updating the configuration settings to a new template or individual settings, a draft configuration is created and  describe-configuration-settings for this environment returns two setting descriptions with different ``DeploymentStatus`` values. 



========
Synopsis
========

::

    update-environment
  [--application-name <value>]
  [--environment-id <value>]
  [--environment-name <value>]
  [--group-name <value>]
  [--description <value>]
  [--tier <value>]
  [--version-label <value>]
  [--template-name <value>]
  [--solution-stack-name <value>]
  [--option-settings <value>]
  [--options-to-remove <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--application-name`` (string)


  The name of the application with which the environment is associated.

  

``--environment-id`` (string)


  The ID of the environment to update.

   

  If no environment with this ID exists, AWS Elastic Beanstalk returns an ``InvalidParameterValue`` error. 

   

  Condition: You must specify either this or an EnvironmentName, or both. If you do not specify either, AWS Elastic Beanstalk returns ``MissingRequiredParameter`` error. 

  

``--environment-name`` (string)


  The name of the environment to update. If no environment with this name exists, AWS Elastic Beanstalk returns an ``InvalidParameterValue`` error. 

   

  Condition: You must specify either this or an EnvironmentId, or both. If you do not specify either, AWS Elastic Beanstalk returns ``MissingRequiredParameter`` error. 

  

``--group-name`` (string)


  The name of the group to which the target environment belongs. Specify a group name only if the environment's name is specified in an environment manifest and not with the environment name or environment ID parameters. See `Environment Manifest (env.yaml)`_ for details.

  

``--description`` (string)


  If this parameter is specified, AWS Elastic Beanstalk updates the description of this environment. 

  

``--tier`` (structure)


  This specifies the tier to use to update the environment. 

   

  Condition: At this time, if you change the tier version, name, or type, AWS Elastic Beanstalk returns ``InvalidParameterValue`` error. 

  



Shorthand Syntax::

    Name=string,Type=string,Version=string




JSON Syntax::

  {
    "Name": "string",
    "Type": "string",
    "Version": "string"
  }



``--version-label`` (string)


  If this parameter is specified, AWS Elastic Beanstalk deploys the named application version to the environment. If no such application version is found, returns an ``InvalidParameterValue`` error. 

  

``--template-name`` (string)


  If this parameter is specified, AWS Elastic Beanstalk deploys this configuration template to the environment. If no such configuration template is found, AWS Elastic Beanstalk returns an ``InvalidParameterValue`` error. 

  

``--solution-stack-name`` (string)


  This specifies the platform version that the environment will run after the environment is updated. 

  

``--option-settings`` (list)


  If specified, AWS Elastic Beanstalk updates the configuration set associated with the running environment and sets the specified configuration options to the requested value. 

  



Shorthand Syntax::

    ResourceName=string,Namespace=string,OptionName=string,Value=string ...




JSON Syntax::

  [
    {
      "ResourceName": "string",
      "Namespace": "string",
      "OptionName": "string",
      "Value": "string"
    }
    ...
  ]



``--options-to-remove`` (list)


  A list of custom user-defined configuration options to remove from the configuration set for this environment. 

  



Shorthand Syntax::

    ResourceName=string,Namespace=string,OptionName=string ...




JSON Syntax::

  [
    {
      "ResourceName": "string",
      "Namespace": "string",
      "OptionName": "string"
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

**To update an environment to a new version**

The following command updates an environment named "my-env" to version "v2" of the application to which it belongs::

  aws elasticbeanstalk update-environment --environment-name my-env --version-label v2

This command requires that the "my-env" environment already exists and belongs to an application that has a valid application version with the label "v2".

Output::

  {
    "ApplicationName": "my-app",
    "EnvironmentName": "my-env",
    "VersionLabel": "v2",
    "Status": "Updating",
    "EnvironmentId": "e-szqipays4h",
    "EndpointURL": "awseb-e-i-AWSEBLoa-1RDLX6TC9VUAO-0123456789.us-west-2.elb.amazonaws.com",
    "SolutionStackName": "64bit Amazon Linux running Tomcat 7",
    "CNAME": "my-env.elasticbeanstalk.com",
    "Health": "Grey",
    "Tier": {
        "Version": " ",
        "Type": "Standard",
        "Name": "WebServer"
    },
    "DateUpdated": "2015-02-03T23:12:29.119Z",
    "DateCreated": "2015-02-03T23:04:54.453Z"
  }

**To set an environment variable**

The following command sets the value of the "PARAM1" variable in the "my-env" environment to "ParamValue"::

  aws elasticbeanstalk update-environment --environment-name my-env --option-settings Namespace=aws:elasticbeanstalk:application:environment,OptionName=PARAM1,Value=ParamValue

The ``option-settings`` parameter takes a namespace in addition to the name and value of the variable. Elastic Beanstalk supports several namespaces for options in addition to environment variables.

**To configure option settings from a file**

The following command configures several options in the ``aws:elb:loadbalancer`` namespace from a file::

  aws elasticbeanstalk update-environment --environment-name my-env --option-settings file://options.json

``options.json`` is a JSON object defining several settings::

  [
    {
      "Namespace": "aws:elb:healthcheck",
      "OptionName": "Interval",
      "Value": "15"
    },
    {
      "Namespace": "aws:elb:healthcheck",
      "OptionName": "Timeout",
      "Value": "8"
    },
    {
      "Namespace": "aws:elb:healthcheck",
      "OptionName": "HealthyThreshold",
      "Value": "2"
    },
    {
      "Namespace": "aws:elb:healthcheck",
      "OptionName": "UnhealthyThreshold",
      "Value": "3"
    }
  ]

Output::

  {
      "ApplicationName": "my-app",
      "EnvironmentName": "my-env",
      "VersionLabel": "7f58-stage-150812_025409",
      "Status": "Updating",
      "EnvironmentId": "e-wtp2rpqsej",
      "EndpointURL": "awseb-e-w-AWSEBLoa-14XB83101Q4L-104QXY80921.sa-east-1.elb.amazonaws.com",
      "SolutionStackName": "64bit Amazon Linux 2015.03 v2.0.0 running Tomcat 8 Java 8",
      "CNAME": "my-env.elasticbeanstalk.com",
      "Health": "Grey",
      "AbortableOperationInProgress": true,
      "Tier": {
          "Version": " ",
          "Type": "Standard",
          "Name": "WebServer"
      },
      "DateUpdated": "2015-08-12T18:15:23.804Z",
      "DateCreated": "2015-08-07T20:48:49.599Z"
  }

For more information about namespaces and supported options, see `Option Values`_ in the *AWS Elastic Beanstalk Developer Guide*.

.. _`Option Values`: http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/command-options.html


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
.. _Health Colors and Statuses: http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/health-enhanced-status.html
