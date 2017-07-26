[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk describe-configuration-settings:


*******************************
describe-configuration-settings
*******************************



===========
Description
===========



Returns a description of the settings for the specified configuration set, that is, either a configuration template or the configuration set associated with a running environment.

 

When describing the settings for the configuration set associated with a running environment, it is possible to receive two sets of setting descriptions. One is the deployed configuration set, and the other is a draft configuration of an environment that is either in the process of deployment or that failed to deploy.

 

Related Topics

 

 
*  delete-environment-configuration   
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/DescribeConfigurationSettings>`_


========
Synopsis
========

::

    describe-configuration-settings
  --application-name <value>
  [--template-name <value>]
  [--environment-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The application for the environment or configuration template.

  

``--template-name`` (string)


  The name of the configuration template to describe.

   

  Conditional: You must specify either this parameter or an EnvironmentName, but not both. If you specify both, AWS Elastic Beanstalk returns an ``InvalidParameterCombination`` error. If you do not specify either, AWS Elastic Beanstalk returns a ``MissingRequiredParameter`` error. 

  

``--environment-name`` (string)


  The name of the environment to describe.

   

  Condition: You must specify either this or a TemplateName, but not both. If you specify both, AWS Elastic Beanstalk returns an ``InvalidParameterCombination`` error. If you do not specify either, AWS Elastic Beanstalk returns ``MissingRequiredParameter`` error. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To view configurations settings for an environment**

The following command retrieves configuration settings for an environment named ``my-env``::

  aws elasticbeanstalk describe-configuration-settings --environment-name my-env --application-name my-app

Output (abbreviated)::

  {
      "ConfigurationSettings": [
          {
              "ApplicationName": "my-app",
              "EnvironmentName": "my-env",
              "Description": "Environment created from the EB CLI using \"eb create\"",
              "DeploymentStatus": "deployed",
              "DateCreated": "2015-08-13T19:16:25Z",
              "OptionSettings": [
                  {
                      "OptionName": "Availability Zones",
                      "ResourceName": "AWSEBAutoScalingGroup",
                      "Namespace": "aws:autoscaling:asg",
                      "Value": "Any"
                  },
                  {
                      "OptionName": "Cooldown",
                      "ResourceName": "AWSEBAutoScalingGroup",
                      "Namespace": "aws:autoscaling:asg",
                      "Value": "360"
                  },
                  ...
                  {
                      "OptionName": "ConnectionDrainingTimeout",
                      "ResourceName": "AWSEBLoadBalancer",
                      "Namespace": "aws:elb:policies",
                      "Value": "20"
                  },
                  {
                      "OptionName": "ConnectionSettingIdleTimeout",
                      "ResourceName": "AWSEBLoadBalancer",
                      "Namespace": "aws:elb:policies",
                      "Value": "60"
                  }
              ],
              "DateUpdated": "2015-08-13T23:30:07Z",
              "SolutionStackName": "64bit Amazon Linux 2015.03 v2.0.0 running Tomcat 8 Java 8"
          }
      ]
  }

For more information about namespaces and supported options, see `Option Values`_ in the *AWS Elastic Beanstalk Developer Guide*.

.. _`Option Values`: http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/command-options.html


======
Output
======

ConfigurationSettings -> (list)

  

  A list of  ConfigurationSettingsDescription . 

  

  (structure)

    

    Describes the settings for a configuration set.

    

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

          

          

        

      

    

  

