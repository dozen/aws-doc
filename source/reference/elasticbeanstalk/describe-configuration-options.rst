[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk describe-configuration-options:


******************************
describe-configuration-options
******************************



===========
Description
===========



Describes the configuration options that are used in a particular configuration template or environment, or that a specified solution stack defines. The description includes the values the options, their default values, and an indication of the required action on a running environment if an option value is changed.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/DescribeConfigurationOptions>`_


========
Synopsis
========

::

    describe-configuration-options
  [--application-name <value>]
  [--template-name <value>]
  [--environment-name <value>]
  [--solution-stack-name <value>]
  [--platform-arn <value>]
  [--options <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The name of the application associated with the configuration template or environment. Only needed if you want to describe the configuration options associated with either the configuration template or environment.

  

``--template-name`` (string)


  The name of the configuration template whose configuration options you want to describe.

  

``--environment-name`` (string)


  The name of the environment whose configuration options you want to describe.

  

``--solution-stack-name`` (string)


  The name of the solution stack whose configuration options you want to describe.

  

``--platform-arn`` (string)


  The ARN of the custom platform.

  

``--options`` (list)


  If specified, restricts the descriptions to only the specified options.

  



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

**To view configuration options for an environment**

The following command retrieves descriptions of all available configuration options for an environment named ``my-env``::

  aws elasticbeanstalk describe-configuration-options --environment-name my-env --application-name my-app

Output (abbreviated)::

  {
      "Options": [
          {
              "Name": "JVMOptions",
              "UserDefined": false,
              "DefaultValue": "Xms=256m,Xmx=256m,XX:MaxPermSize=64m,JVM Options=",
              "ChangeSeverity": "RestartApplicationServer",
              "Namespace": "aws:cloudformation:template:parameter",
              "ValueType": "KeyValueList"
          },
          {
              "Name": "Interval",
              "UserDefined": false,
              "DefaultValue": "30",
              "ChangeSeverity": "NoInterruption",
              "Namespace": "aws:elb:healthcheck",
              "MaxValue": 300,
              "MinValue": 5,
              "ValueType": "Scalar"
          },
          ...
          {
              "Name": "LowerThreshold",
              "UserDefined": false,
              "DefaultValue": "2000000",
              "ChangeSeverity": "NoInterruption",
              "Namespace": "aws:autoscaling:trigger",
              "MinValue": 0,
              "ValueType": "Scalar"
          },
          {
              "Name": "ListenerEnabled",
              "UserDefined": false,
              "DefaultValue": "true",
              "ChangeSeverity": "Unknown",
              "Namespace": "aws:elb:listener",
              "ValueType": "Boolean"
          }
      ]
  }

Available configuration options vary per platform and configuration version. For more information about namespaces and supported options, see `Option Values`_ in the *AWS Elastic Beanstalk Developer Guide*.

.. _`Option Values`: http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/command-options.html


======
Output
======

SolutionStackName -> (string)

  

  The name of the solution stack these configuration options belong to.

  

  

PlatformArn -> (string)

  

  The ARN of the custom platform.

  

  

Options -> (list)

  

  A list of  ConfigurationOptionDescription . 

  

  (structure)

    

    Describes the possible values for a configuration option.

    

    Namespace -> (string)

      

      A unique namespace identifying the option's associated AWS resource.

      

      

    Name -> (string)

      

      The name of the configuration option.

      

      

    DefaultValue -> (string)

      

      The default value for this configuration option.

      

      

    ChangeSeverity -> (string)

      

      An indication of which action is required if the value for this configuration option changes:

       

       
      * ``NoInterruption`` : There is no interruption to the environment or application availability. 
       
      * ``RestartEnvironment`` : The environment is entirely restarted, all AWS resources are deleted and recreated, and the environment is unavailable during the process. 
       
      * ``RestartApplicationServer`` : The environment is available the entire time. However, a short application outage occurs when the application servers on the running Amazon EC2 instances are restarted. 
       

      

      

    UserDefined -> (boolean)

      

      An indication of whether the user defined this configuration option:

       

       
      * ``true`` : This configuration option was defined by the user. It is a valid choice for specifying if this as an ``Option to Remove`` when updating configuration settings.  
       
      * ``false`` : This configuration was not defined by the user. 
       

       

      Constraint: You can remove only ``UserDefined`` options from a configuration. 

       

      Valid Values: ``true`` | ``false``  

      

      

    ValueType -> (string)

      

      An indication of which type of values this option has and whether it is allowable to select one or more than one of the possible values:

       

       
      * ``Scalar`` : Values for this option are a single selection from the possible values, or an unformatted string, or numeric value governed by the ``MIN/MAX/Regex`` constraints. 
       
      * ``List`` : Values for this option are multiple selections from the possible values. 
       
      * ``Boolean`` : Values for this option are either ``true`` or ``false`` . 
       
      * ``Json`` : Values for this option are a JSON representation of a ``ConfigDocument`` . 
       

      

      

    ValueOptions -> (list)

      

      If specified, values for the configuration option are selected from this list.

      

      (string)

        

        

      

    MinValue -> (integer)

      

      If specified, the configuration option must be a numeric value greater than this value.

      

      

    MaxValue -> (integer)

      

      If specified, the configuration option must be a numeric value less than this value.

      

      

    MaxLength -> (integer)

      

      If specified, the configuration option must be a string value no longer than this value.

      

      

    Regex -> (structure)

      

      If specified, the configuration option must be a string value that satisfies this regular expression.

      

      Pattern -> (string)

        

        The regular expression pattern that a string configuration option value with this restriction must match.

        

        

      Label -> (string)

        

        A unique name representing this regular expression.

        

        

      

    

  

