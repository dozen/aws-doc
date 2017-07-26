[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk describe-environment-resources:


******************************
describe-environment-resources
******************************



===========
Description
===========



Returns AWS resources for this environment.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/DescribeEnvironmentResources>`_


========
Synopsis
========

::

    describe-environment-resources
  [--environment-id <value>]
  [--environment-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--environment-id`` (string)


  The ID of the environment to retrieve AWS resource usage data.

   

  Condition: You must specify either this or an EnvironmentName, or both. If you do not specify either, AWS Elastic Beanstalk returns ``MissingRequiredParameter`` error. 

  

``--environment-name`` (string)


  The name of the environment to retrieve AWS resource usage data.

   

  Condition: You must specify either this or an EnvironmentId, or both. If you do not specify either, AWS Elastic Beanstalk returns ``MissingRequiredParameter`` error. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To view information about the AWS resources in your environment**

The following command retrieves information about resources in an environment named ``my-env``::

  aws elasticbeanstalk describe-environment-resources --environment-name my-env

Output::

  {
      "EnvironmentResources": {
          "EnvironmentName": "my-env",
          "AutoScalingGroups": [
              {
                  "Name": "awseb-e-qu3fyyjyjs-stack-AWSEBAutoScalingGroup-QSB2ZO88SXZT"
              }
          ],
          "Triggers": [],
          "LoadBalancers": [
              {
                  "Name": "awseb-e-q-AWSEBLoa-1EEPZ0K98BIF0"
              }
          ],
          "Queues": [],
          "Instances": [
              {
                  "Id": "i-0c91c786"
              }
          ],
          "LaunchConfigurations": [
              {
                  "Name": "awseb-e-qu3fyyjyjs-stack-AWSEBAutoScalingLaunchConfiguration-1UUVQIBC96TQ2"
              }
          ]
      }
  }


======
Output
======

EnvironmentResources -> (structure)

  

  A list of  EnvironmentResourceDescription . 

  

  EnvironmentName -> (string)

    

    The name of the environment.

    

    

  AutoScalingGroups -> (list)

    

    The ``AutoScalingGroups`` used by this environment. 

    

    (structure)

      

      Describes an Auto Scaling launch configuration.

      

      Name -> (string)

        

        The name of the ``AutoScalingGroup`` . 

        

        

      

    

  Instances -> (list)

    

    The Amazon EC2 instances used by this environment.

    

    (structure)

      

      The description of an Amazon EC2 instance.

      

      Id -> (string)

        

        The ID of the Amazon EC2 instance.

        

        

      

    

  LaunchConfigurations -> (list)

    

    The Auto Scaling launch configurations in use by this environment.

    

    (structure)

      

      Describes an Auto Scaling launch configuration.

      

      Name -> (string)

        

        The name of the launch configuration.

        

        

      

    

  LoadBalancers -> (list)

    

    The LoadBalancers in use by this environment.

    

    (structure)

      

      Describes a LoadBalancer.

      

      Name -> (string)

        

        The name of the LoadBalancer.

        

        

      

    

  Triggers -> (list)

    

    The ``AutoScaling`` triggers in use by this environment. 

    

    (structure)

      

      Describes a trigger.

      

      Name -> (string)

        

        The name of the trigger.

        

        

      

    

  Queues -> (list)

    

    The queues used by this environment.

    

    (structure)

      

      Describes a queue.

      

      Name -> (string)

        

        The name of the queue.

        

        

      URL -> (string)

        

        The URL of the queue.

        

        

      

    

  

