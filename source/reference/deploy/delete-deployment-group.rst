[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy delete-deployment-group:


***********************
delete-deployment-group
***********************



===========
Description
===========



Deletes a deployment group.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/DeleteDeploymentGroup>`_


========
Synopsis
========

::

    delete-deployment-group
  --application-name <value>
  --deployment-group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The name of an AWS CodeDeploy application associated with the applicable IAM user or AWS account.

  

``--deployment-group-name`` (string)


  The name of an existing deployment group for the specified application.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a deployment group**

This example deletes a deployment group that is associated with the specified application.

Command::

  aws deploy delete-deployment-group --application-name WordPress_App --deployment-group-name WordPress_DG

Output::

  {
      "hooksNotCleanedUp": []
  }

======
Output
======

hooksNotCleanedUp -> (list)

  

  If the output contains no data, and the corresponding deployment group contained at least one Auto Scaling group, AWS CodeDeploy successfully removed all corresponding Auto Scaling lifecycle event hooks from the Amazon EC2 instances in the Auto Scaling group. If the output contains data, AWS CodeDeploy could not remove some Auto Scaling lifecycle event hooks from the Amazon EC2 instances in the Auto Scaling group.

  

  (structure)

    

    Information about an Auto Scaling group.

    

    name -> (string)

      

      The Auto Scaling group name.

      

      

    hook -> (string)

      

      An Auto Scaling lifecycle event hook name.

      

      

    

  

