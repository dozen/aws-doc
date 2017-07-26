[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk update-configuration-template:


*****************************
update-configuration-template
*****************************



===========
Description
===========



Updates the specified configuration template to have the specified properties or configuration option values.

 

.. note::

   

  If a property (for example, ``application-name`` ) is not provided, its value remains unchanged. To clear such properties, specify an empty string.

   

 

Related Topics

 

 
*  describe-configuration-options   
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/UpdateConfigurationTemplate>`_


========
Synopsis
========

::

    update-configuration-template
  --application-name <value>
  --template-name <value>
  [--description <value>]
  [--option-settings <value>]
  [--options-to-remove <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The name of the application associated with the configuration template to update.

   

  If no application is found with this name, ``update-configuration-template`` returns an ``InvalidParameterValue`` error. 

  

``--template-name`` (string)


  The name of the configuration template to update.

   

  If no configuration template is found with this name, ``update-configuration-template`` returns an ``InvalidParameterValue`` error. 

  

``--description`` (string)


  A new description for the configuration.

  

``--option-settings`` (list)


  A list of configuration option settings to update with the new specified option value.

  



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


  A list of configuration options to remove from the configuration set.

   

  Constraint: You can remove only ``UserDefined`` configuration options. 

  



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

**To update a configuration template**

The following command removes the configured CloudWatch custom health metrics configuration ``ConfigDocument`` from a saved configuration template named ``my-template``::

  aws elasticbeanstalk update-configuration-template --template-name my-template --application-name my-app --options-to-remove Namespace=aws:elasticbeanstalk:healthreporting:system,OptionName=ConfigDocument

Output::

  {
      "ApplicationName": "my-app",
      "TemplateName": "my-template",
      "DateCreated": "2015-08-20T22:39:31Z",
      "DateUpdated": "2015-08-20T22:43:11Z",
      "SolutionStackName": "64bit Amazon Linux 2015.03 v2.0.0 running Tomcat 8 Java 8"
  }

For more information about namespaces and supported options, see `Option Values`_ in the *AWS Elastic Beanstalk Developer Guide*.

.. _`Option Values`: http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/command-options.html


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

      

      

    

  

