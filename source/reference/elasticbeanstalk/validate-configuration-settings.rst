[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk validate-configuration-settings:


*******************************
validate-configuration-settings
*******************************



===========
Description
===========



Takes a set of configuration settings and either a configuration template or environment, and determines whether those values are valid.

 

This action returns a list of messages indicating any errors or warnings associated with the selection of option values.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/ValidateConfigurationSettings>`_


========
Synopsis
========

::

    validate-configuration-settings
  --application-name <value>
  [--template-name <value>]
  [--environment-name <value>]
  --option-settings <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The name of the application that the configuration template or environment belongs to.

  

``--template-name`` (string)


  The name of the configuration template to validate the settings against.

   

  Condition: You cannot specify both this and an environment name.

  

``--environment-name`` (string)


  The name of the environment to validate the settings against.

   

  Condition: You cannot specify both this and a configuration template name.

  

``--option-settings`` (list)


  A list of the options and desired values to evaluate.

  



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

**To validate configuration settings**

The following command validates a CloudWatch custom metrics config document::

  aws elasticbeanstalk validate-configuration-settings --application-name my-app --environment-name my-env --option-settings file://options.json

``options.json`` is a JSON document that includes one or more configuration settings to validate::

  [
      {
          "Namespace": "aws:elasticbeanstalk:healthreporting:system",
          "OptionName": "ConfigDocument",
          "Value": "{\"CloudWatchMetrics\": {\"Environment\": {\"ApplicationLatencyP99.9\": null,\"InstancesSevere\": 60,\"ApplicationLatencyP90\": 60,\"ApplicationLatencyP99\": null,\"ApplicationLatencyP95\": 60,\"InstancesUnknown\": 60,\"ApplicationLatencyP85\": 60,\"InstancesInfo\": null,\"ApplicationRequests2xx\": null,\"InstancesDegraded\": null,\"InstancesWarning\": 60,\"ApplicationLatencyP50\": 60,\"ApplicationRequestsTotal\": null,\"InstancesNoData\": null,\"InstancesPending\": 60,\"ApplicationLatencyP10\": null,\"ApplicationRequests5xx\": null,\"ApplicationLatencyP75\": null,\"InstancesOk\": 60,\"ApplicationRequests3xx\": null,\"ApplicationRequests4xx\": null},\"Instance\": {\"ApplicationLatencyP99.9\": null,\"ApplicationLatencyP90\": 60,\"ApplicationLatencyP99\": null,\"ApplicationLatencyP95\": null,\"ApplicationLatencyP85\": null,\"CPUUser\": 60,\"ApplicationRequests2xx\": null,\"CPUIdle\": null,\"ApplicationLatencyP50\": null,\"ApplicationRequestsTotal\": 60,\"RootFilesystemUtil\": null,\"LoadAverage1min\": null,\"CPUIrq\": null,\"CPUNice\": 60,\"CPUIowait\": 60,\"ApplicationLatencyP10\": null,\"LoadAverage5min\": null,\"ApplicationRequests5xx\": null,\"ApplicationLatencyP75\": 60,\"CPUSystem\": 60,\"ApplicationRequests3xx\": 60,\"ApplicationRequests4xx\": null,\"InstanceHealth\": null,\"CPUSoftirq\": 60}},\"Version\": 1}"
      }
  ]

If the options that you specify are valid for the specified environment, Elastic Beanstalk returns an empty Messages array::

  {
      "Messages": []
  }

If validation fails, the response will include information about the error::

  {
      "Messages": [
          {
              "OptionName": "ConfigDocumet",
              "Message": "Invalid option specification (Namespace: 'aws:elasticbeanstalk:healthreporting:system', OptionName: 'ConfigDocumet'): Unknown configuration setting.",
              "Namespace": "aws:elasticbeanstalk:healthreporting:system",
              "Severity": "error"
          }
      ]
  }


For more information about namespaces and supported options, see `Option Values`_ in the *AWS Elastic Beanstalk Developer Guide*.

.. _`Option Values`: http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/command-options.html


======
Output
======

Messages -> (list)

  

  A list of  ValidationMessage . 

  

  (structure)

    

    An error or warning for a desired configuration option value.

    

    Message -> (string)

      

      A message describing the error or warning.

      

      

    Severity -> (string)

      

      An indication of the severity of this message:

       

       
      * ``error`` : This message indicates that this is not a valid setting for an option. 
       
      * ``warning`` : This message is providing information you should take into account. 
       

      

      

    Namespace -> (string)

      

      The namespace to which the option belongs.

      

      

    OptionName -> (string)

      

      The name of the option.

      

      

    

  

