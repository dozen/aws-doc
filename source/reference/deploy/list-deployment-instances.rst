[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy list-deployment-instances:


*************************
list-deployment-instances
*************************



===========
Description
===========



Lists the instances for a deployment associated with the applicable IAM user or AWS account.



========
Synopsis
========

::

    list-deployment-instances
  --deployment-id <value>
  [--next-token <value>]
  [--instance-status-filter <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--deployment-id`` (string)


  The unique ID of a deployment.

  

``--next-token`` (string)


  An identifier that was returned from the previous list deployment instances call, which can be used to return the next set of deployment instances in the list.

  

``--instance-status-filter`` (list)


  A subset of instances to list, by status:

   

   
  * Pending: Include in the resulting list those instances with pending deployments.
   
  * InProgress: Include in the resulting list those instances with in-progress deployments.
   
  * Succeeded: Include in the resulting list those instances with succeeded deployments.
   
  * Failed: Include in the resulting list those instances with failed deployments.
   
  * Skipped: Include in the resulting list those instances with skipped deployments.
   
  * Unknown: Include in the resulting list those instances with deployments in an unknown state.
   

  



Syntax::

  "string" "string" ...

  Where valid values are:
    Pending
    InProgress
    Succeeded
    Failed
    Skipped
    Unknown





``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get information about deployment instances**

This example displays information about all deployment instances that are associated with the specified deployment.

Command::

  aws deploy list-deployment-instances --deployment-id d-9DI6I4EX --instance-status-filter Succeeded

Output::

  {
      "instancesList": [
          "i-8c4490EX",
		  "i-7d5389EX"
      ]
  }

======
Output
======

instancesList -> (list)

  

  A list of instances IDs.

  

  (string)

    

    

  

nextToken -> (string)

  

  If the amount of information that is returned is significantly large, an identifier will also be returned, which can be used in a subsequent list deployment instances call to return the next set of deployment instances in the list.

  

  

