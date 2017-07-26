[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk create-configuration-template:


*****************************
create-configuration-template
*****************************



===========
Description
===========



Creates a configuration template. Templates are associated with a specific application and are used to deploy different versions of the application with the same configuration settings.

 

Related Topics

 

 
*  describe-configuration-options   
 
*  describe-configuration-settings   
 
*  list-available-solution-stacks   
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/CreateConfigurationTemplate>`_


========
Synopsis
========

::

    create-configuration-template
  --application-name <value>
  --template-name <value>
  [--solution-stack-name <value>]
  [--platform-arn <value>]
  [--source-configuration <value>]
  [--environment-id <value>]
  [--description <value>]
  [--option-settings <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The name of the application to associate with this configuration template. If no application is found with this name, AWS Elastic Beanstalk returns an ``InvalidParameterValue`` error. 

  

``--template-name`` (string)


  The name of the configuration template.

   

  Constraint: This name must be unique per application.

   

  Default: If a configuration template already exists with this name, AWS Elastic Beanstalk returns an ``InvalidParameterValue`` error. 

  

``--solution-stack-name`` (string)


  The name of the solution stack used by this configuration. The solution stack specifies the operating system, architecture, and application server for a configuration template. It determines the set of configuration options as well as the possible and default values.

   

  Use  list-available-solution-stacks to obtain a list of available solution stacks. 

   

  A solution stack name or a source configuration parameter must be specified, otherwise AWS Elastic Beanstalk returns an ``InvalidParameterValue`` error. 

   

  If a solution stack name is not specified and the source configuration parameter is specified, AWS Elastic Beanstalk uses the same solution stack as the source configuration template.

  

``--platform-arn`` (string)


  The ARN of the custome platform.

  

``--source-configuration`` (structure)


  If specified, AWS Elastic Beanstalk uses the configuration values from the specified configuration template to create a new configuration.

   

  Values specified in the ``OptionSettings`` parameter of this call overrides any values obtained from the ``source-configuration`` . 

   

  If no configuration template is found, returns an ``InvalidParameterValue`` error. 

   

  Constraint: If both the solution stack name parameter and the source configuration parameters are specified, the solution stack of the source configuration template must match the specified solution stack name or else AWS Elastic Beanstalk returns an ``InvalidParameterCombination`` error. 

  



Shorthand Syntax::

    ApplicationName=string,TemplateName=string




JSON Syntax::

  {
    "ApplicationName": "string",
    "TemplateName": "string"
  }



``--environment-id`` (string)


  The ID of the environment used with this configuration template.

  

``--description`` (string)


  Describes this configuration.

  

``--option-settings`` (list)


  If specified, AWS Elastic Beanstalk sets the specified configuration option to the requested value. The new value overrides the value obtained from the solution stack or the source configuration template.

  



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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a configuration template**

The following command creates a configuration template named ``my-app-v1`` from the settings applied to an environment with the id ``e-rpqsewtp2j``::

  aws elasticbeanstalk create-configuration-template --application-name my-app --template-name my-app-v1 --environment-id e-rpqsewtp2j

Output::

  {
      "ApplicationName": "my-app",
      "TemplateName": "my-app-v1",
      "DateCreated": "2015-08-12T18:40:39Z",
      "DateUpdated": "2015-08-12T18:40:39Z",
      "SolutionStackName": "64bit Amazon Linux 2015.03 v2.0.0 running Tomcat 8 Java 8"
  }


======
Output
======

SolutionStackName -> (string)

  

  The name of the solution stack this configuration set uses.

  

  

PlatformArn -> (string)

  

  The ARN of the custom platform.

  

  

ApplicationName -> (string)

  

  The name of the application associated with this configuration set.

  

  

TemplateName -> (string)

  

  If not ``null`` , the name of the configuration template for this configuration set. 

  

  

Description -> (string)

  

  Describes this configuration set.

  

  

EnvironmentName -> (string)

  

  If not ``null`` , the name of the environment for this configuration set. 

  

  

DeploymentStatus -> (string)

  

  If this configuration set is associated with an environment, the ``DeploymentStatus`` parameter indicates the deployment status of this configuration set: 

   

   
  * ``null`` : This configuration is not associated with a running environment. 
   
  * ``pending`` : This is a draft configuration that is not deployed to the associated environment but is in the process of deploying. 
   
  * ``deployed`` : This is the configuration that is currently deployed to the associated running environment. 
   
  * ``failed`` : This is a draft configuration that failed to successfully deploy. 
   

  

  

DateCreated -> (timestamp)

  

  The date (in UTC time) when this configuration set was created.

  

  

DateUpdated -> (timestamp)

  

  The date (in UTC time) when this configuration set was last modified.

  

  

OptionSettings -> (list)

  

  A list of the configuration options and their values in this configuration set.

  

  (structure)

    

    A specification identifying an individual configuration option along with its current value. For a list of possible option values, go to `Option Values <http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/command-options.html>`_ in the *AWS Elastic Beanstalk Developer Guide* . 

    

    ResourceName -> (string)

      

      A unique resource name for a time-based scaling configuration option.

      

      

    Namespace -> (string)

      

      A unique namespace identifying the option's associated AWS resource.

      

      

    OptionName -> (string)

      

      The name of the configuration option.

      

      

    Value -> (string)

      

      The current value for the configuration option.

      

      

    

  

