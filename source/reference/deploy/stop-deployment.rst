[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy stop-deployment:


***************
stop-deployment
***************



===========
Description
===========



Attempts to stop an ongoing deployment.



========
Synopsis
========

::

    stop-deployment
  --deployment-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--deployment-id`` (string)


  The unique ID of a deployment.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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
   
  * Succeeded: The stop operation succeeded.
   

  

  

statusMessage -> (string)

  

  An accompanying status message.

  

  

