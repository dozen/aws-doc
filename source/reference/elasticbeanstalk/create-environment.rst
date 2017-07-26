[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk create-environment:


******************
create-environment
******************



===========
Description
===========



Launches an environment for the specified application using the specified configuration.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/CreateEnvironment>`_


========
Synopsis
========

::

    create-environment
  --application-name <value>
  [--environment-name <value>]
  [--group-name <value>]
  [--description <value>]
  [--cname-prefix <value>]
  [--tier <value>]
  [--tags <value>]
  [--version-label <value>]
  [--template-name <value>]
  [--solution-stack-name <value>]
  [--platform-arn <value>]
  [--option-settings <value>]
  [--options-to-remove <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The name of the application that contains the version to be deployed.

   

  If no application is found with this name, ``create-environment`` returns an ``InvalidParameterValue`` error. 

  

``--environment-name`` (string)


  A unique name for the deployment environment. Used in the application URL.

   

  Constraint: Must be from 4 to 40 characters in length. The name can contain only letters, numbers, and hyphens. It cannot start or end with a hyphen. This name must be unique in your account. If the specified name already exists, AWS Elastic Beanstalk returns an ``InvalidParameterValue`` error. 

   

  Default: If the CNAME parameter is not specified, the environment name becomes part of the CNAME, and therefore part of the visible URL for your application.

  

``--group-name`` (string)


  The name of the group to which the target environment belongs. Specify a group name only if the environment's name is specified in an environment manifest and not with the environment name parameter. See `Environment Manifest (env.yaml) <http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/environment-cfg-manifest.html>`_ for details.

  

``--description`` (string)


  Describes this environment.

  

``--cname-prefix`` (string)


  If specified, the environment attempts to use this value as the prefix for the CNAME. If not specified, the CNAME is generated automatically by appending a random alphanumeric string to the environment name.

  

``--tier`` (structure)


  This specifies the tier to use for creating this environment.

  



Shorthand Syntax::

    Name=string,Type=string,Version=string




JSON Syntax::

  {
    "Name": "string",
    "Type": "string",
    "Version": "string"
  }



``--tags`` (list)


  This specifies the tags applied to resources in the environment.

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
    }
    ...
  ]



``--version-label`` (string)


  The name of the application version to deploy.

   

  If the specified application has no associated application versions, AWS Elastic Beanstalk ``update-environment`` returns an ``InvalidParameterValue`` error. 

   

  Default: If not specified, AWS Elastic Beanstalk attempts to launch the sample application in the container.

  

``--template-name`` (string)


  The name of the configuration template to use in deployment. If no configuration template is found with this name, AWS Elastic Beanstalk returns an ``InvalidParameterValue`` error. 

  

``--solution-stack-name`` (string)


  This is an alternative to specifying a template name. If specified, AWS Elastic Beanstalk sets the configuration values to the default values associated with the specified solution stack.

  

``--platform-arn`` (string)


  The ARN of the custom platform.

  

``--option-settings`` (list)


  If specified, AWS Elastic Beanstalk sets the specified configuration options to the requested value in the configuration set for the new environment. These override the values obtained from the solution stack or the configuration template.

  



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


  A list of custom user-defined configuration options to remove from the configuration set for this new environment.

  



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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a new environment for an application**

The following command creates a new environment for version "v1" of a java application named "my-app"::

  aws elasticbeanstalk create-environment --application-name my-app --environment-name my-env --cname-prefix my-app --version-label v1 --solution-stack-name "64bit Amazon Linux 2015.03 v2.0.0 running Tomcat 8 Java 8"

Output::

  {
    "ApplicationName": "my-app",
    "EnvironmentName": "my-env",
    "VersionLabel": "v1",
    "Status": "Launching",
    "EnvironmentId": "e-izqpassy4h",
    "SolutionStackName": "64bit Amazon Linux 2015.03 v2.0.0 running Tomcat 8 Java 8",
    "CNAME": "my-app.elasticbeanstalk.com",
    "Health": "Grey",
    "Tier": {
        "Type": "Standard",
        "Name": "WebServer",
        "Version": " "
    },
    "DateUpdated": "2015-02-03T23:04:54.479Z",
    "DateCreated": "2015-02-03T23:04:54.479Z"
  }

``v1`` is the label of an application version previously uploaded with `create-application-version`_.

.. _`create-application-version`: http://docs.aws.amazon.com/cli/latest/reference/elasticbeanstalk/create-application-version.html

**To specify a JSON file to define environment configuration options**

The following ``create-environment`` command specifies that a JSON file with the name ``myoptions.json`` should be used to override values obtained from the solution stack or the configuration template::

  aws elasticbeanstalk create-environment --environment-name sample-env --application-name sampleapp --option-settings file://myoptions.json

For more information, see `Option Values`_ in the *AWS Elastic Beanstalk Developer Guide*.

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

      

      

    

  

