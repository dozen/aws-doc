[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy stop-deployment:


***************
stop-deployment
***************



===========
Description
===========



Attempts to stop an ongoing deployment.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/StopDeployment>`_


========
Synopsis
========

::

    stop-deployment
  --deployment-id <value>
  [--auto-rollback-enabled | --no-auto-rollback-enabled]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--deployment-id`` (string)


  The unique ID of a deployment.

  

``--auto-rollback-enabled`` | ``--no-auto-rollback-enabled`` (boolean)


  Indicates, when a deployment is stopped, whether instances that have been updated should be rolled back to the previous version of the application revision.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To attempt to stop a deployment**

This example attempts to stop an in-progress deployment that is associated with the user's AWS account.

Command::

  aws deploy stop-deployment --deployment-id d-8365D4OEX

Output::

  {
      "status": "Succeeded", 
      "statusMessage": "No more commands will be scheduled for execution in the deployment instances"
  }

======
Output
======

status -> (string)

  

  The status of the stop deployment operation:

   

   
  * Pending: The stop operation is pending. 
   
  * Succeeded: The stop operation was successful. 
   

  

  

statusMessage -> (string)

  

  An accompanying status message.

  

  

