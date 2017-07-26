[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy list-deployment-groups:


**********************
list-deployment-groups
**********************



===========
Description
===========



Lists the deployment groups for an application registered with the applicable IAM user or AWS account.



========
Synopsis
========

::

    list-deployment-groups
  --application-name <value>
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--application-name`` (string)


  The name of an existing AWS CodeDeploy application associated with the applicable IAM user or AWS account.

  

``--next-token`` (string)


  An identifier that was returned from the previous list deployment groups call, which can be used to return the next set of deployment groups in the list.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get information about deployment groups**

This example displays information about all deployment groups that are associated with the specified application.

Command::

  aws deploy list-deployment-groups --application-name WordPress_App

Output::

  {
      "applicationName": "WordPress_App",
      "deploymentGroups": [
          "WordPress_DG",
		  "WordPress_Beta_DG"
      ]
  }

======
Output
======

applicationName -> (string)

  

  The application name.

  

  

deploymentGroups -> (list)

  

  A list of corresponding deployment group names.

  

  (string)

    

    

  

nextToken -> (string)

  

  If the amount of information that is returned is significantly large, an identifier will also be returned, which can be used in a subsequent list deployment groups call to return the next set of deployment groups in the list.

  

  

