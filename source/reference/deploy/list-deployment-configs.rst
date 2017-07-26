[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy list-deployment-configs:


***********************
list-deployment-configs
***********************



===========
Description
===========



Lists the deployment configurations with the applicable IAM user or AWS account.



========
Synopsis
========

::

    list-deployment-configs
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--next-token`` (string)


  An identifier that was returned from the previous list deployment configurations call, which can be used to return the next set of deployment configurations in the list.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get information about deployment configurations**

This example displays information about all deployment configurations that are associated with the user's AWS account.

Command::

  aws deploy list-deployment-configs

Output::

  {
      "deploymentConfigsList": [
          "ThreeQuartersHealthy",
          "CodeDeployDefault.AllAtOnce",
          "CodeDeployDefault.HalfAtATime",
          "CodeDeployDefault.OneAtATime"
      ]
  }

======
Output
======

deploymentConfigsList -> (list)

  

  A list of deployment configurations, including the built-in configurations such as CodeDeployDefault.OneAtATime.

  

  (string)

    

    

  

nextToken -> (string)

  

  If the amount of information that is returned is significantly large, an identifier will also be returned, which can be used in a subsequent list deployment configurations call to return the next set of deployment configurations in the list.

  

  

