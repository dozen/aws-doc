[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy get-deployment-config:


*********************
get-deployment-config
*********************



===========
Description
===========



Gets information about a deployment configuration.



========
Synopsis
========

::

    get-deployment-config
  --deployment-config-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--deployment-config-name`` (string)


  The name of an existing deployment configuration associated with the applicable IAM user or AWS account.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

    

    Information about the number or percentage of minimum healthy instances.

    

    value -> (integer)

      

      The minimum healthy instances value.

      

      

    type -> (string)

      

      The minimum healthy instances type:

       

       
      * HOST_COUNT: The minimum number of healthy instances, as an absolute value.
       
      * FLEET_PERCENT: The minimum number of healthy instances, as a percentage of the total number of instances in the deployment.
       

       

      For example, for 9 instances, if a HOST_COUNT of 6 is specified, deploy to up to 3 instances at a time. The deployment succeeds if 6 or more instances are successfully deployed to; otherwise, the deployment fails. If a FLEET_PERCENT of 40 is specified, deploy to up to 5 instances at a time. The deployment succeeds if 4 or more instances are successfully deployed to; otherwise, the deployment fails.

       

      .. note::

        In a call to the get deployment configuration operation, CodeDeployDefault.OneAtATime will return a minimum healthy instances type of MOST_CONCURRENCY and a value of 1. This means a deployment to only one instance at a time. (You cannot set the type to MOST_CONCURRENCY, only to HOST_COUNT or FLEET_PERCENT.) In addition, with CodeDeployDefault.OneAtATime, AWS CodeDeploy will try to ensure that all but one instance are kept in healthy states during the deployment operation. While this allows one instance at a time to be taken offline for a new deployment, it also means that if the deployment to the last instance fails, the overall deployment still succeeds.

      

      

    

  createTime -> (timestamp)

    

    The time that the deployment configuration was created.

    

    

  

