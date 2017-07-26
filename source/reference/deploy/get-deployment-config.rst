[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy get-deployment-config:


*********************
get-deployment-config
*********************



===========
Description
===========



Gets information about a deployment configuration.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/GetDeploymentConfig>`_


========
Synopsis
========

::

    get-deployment-config
  --deployment-config-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--deployment-config-name`` (string)


  The name of a deployment configuration associated with the applicable IAM user or AWS account.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get information about a deployment configuration**

This example displays information about a deployment configuration that is associated with the user's AWS account.

Command::

  aws deploy get-deployment-config --deployment-config-name ThreeQuartersHealthy

Output::

  {
      "deploymentConfigInfo": {
          "deploymentConfigId": "bf6b390b-61d3-4f24-8911-a1664EXAMPLE",
          "minimumHealthyHosts": {
              "type": "FLEET_PERCENT",
              "value": 75
          },
          "createTime": 1411081164.379,
          "deploymentConfigName": "ThreeQuartersHealthy"
      }
  }

======
Output
======

deploymentConfigInfo -> (structure)

  

  Information about the deployment configuration.

  

  deploymentConfigId -> (string)

    

    The deployment configuration ID.

    

    

  deploymentConfigName -> (string)

    

    The deployment configuration name.

    

    

  minimumHealthyHosts -> (structure)

    

    Information about the number or percentage of minimum healthy instance.

    

    value -> (integer)

      

      The minimum healthy instance value.

      

      

    type -> (string)

      

      The minimum healthy instance type:

       

       
      * HOST_COUNT: The minimum number of healthy instance as an absolute value. 
       
      * FLEET_PERCENT: The minimum number of healthy instance as a percentage of the total number of instance in the deployment. 
       

       

      In an example of nine instance, if a HOST_COUNT of six is specified, deploy to up to three instances at a time. The deployment will be successful if six or more instances are deployed to successfully; otherwise, the deployment fails. If a FLEET_PERCENT of 40 is specified, deploy to up to five instance at a time. The deployment will be successful if four or more instance are deployed to successfully; otherwise, the deployment fails.

       

      .. note::

         

        In a call to the get deployment configuration operation, CodeDeployDefault.OneAtATime will return a minimum healthy instance type of MOST_CONCURRENCY and a value of 1. This means a deployment to only one instance at a time. (You cannot set the type to MOST_CONCURRENCY, only to HOST_COUNT or FLEET_PERCENT.) In addition, with CodeDeployDefault.OneAtATime, AWS CodeDeploy will try to ensure that all instances but one are kept in a healthy state during the deployment. Although this allows one instance at a time to be taken offline for a new deployment, it also means that if the deployment to the last instance fails, the overall deployment still succeeds.

         

       

      For more information, see `AWS CodeDeploy Instance Health <http://docs.aws.amazon.com/codedeploy/latest/userguide/instances-health.html>`_ in the *AWS CodeDeploy User Guide* .

      

      

    

  createTime -> (timestamp)

    

    The time at which the deployment configuration was created.

    

    

  

