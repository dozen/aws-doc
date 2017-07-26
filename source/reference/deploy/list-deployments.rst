[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy list-deployments:


****************
list-deployments
****************



===========
Description
===========



Lists the deployments within a deployment group for an application registered with the applicable IAM user or AWS account.



========
Synopsis
========

::

    list-deployments
  [--application-name <value>]
  [--deployment-group-name <value>]
  [--include-only-statuses <value>]
  [--create-time-range <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--application-name`` (string)


  The name of an existing AWS CodeDeploy application associated with the applicable IAM user or AWS account.

  

``--deployment-group-name`` (string)


  The name of an existing deployment group for the specified application.

  

``--include-only-statuses`` (list)


  A subset of deployments to list, by status:

   

   
  * Created: Include in the resulting list created deployments.
   
  * Queued: Include in the resulting list queued deployments.
   
  * In Progress: Include in the resulting list in-progress deployments.
   
  * Succeeded: Include in the resulting list succeeded deployments.
   
  * Failed: Include in the resulting list failed deployments.
   
  * Aborted: Include in the resulting list aborted deployments.
   

  



Syntax::

  "string" "string" ...

  Where valid values are:
    Created
    Queued
    InProgress
    Succeeded
    Failed
    Stopped





``--create-time-range`` (structure)


  A deployment creation start- and end-time range for returning a subset of the list of deployments.

  



Shorthand Syntax::

    start=timestamp,end=timestamp




JSON Syntax::

  {
    "start": timestamp,
    "end": timestamp
  }



``--next-token`` (string)


  An identifier that was returned from the previous list deployments call, which can be used to return the next set of deployments in the list.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get information about deployments**

This example displays information about all deployments that are associated with the specified application and deployment group.

Command::

  aws deploy list-deployments --application-name WordPress_App --create-time-range start=2014-08-19T00:00:00,end=2014-08-20T00:00:00 --deployment-group-name WordPress_DG --include-only-statuses Failed

Output::

  {
      "deployments": [
          "d-QA4G4F9EX",
          "d-1MVNYOEEX",
          "d-WEWRE8BEX"
      ]
  }

======
Output
======

deployments -> (list)

  

  A list of deployment IDs.

  

  (string)

    

    

  

nextToken -> (string)

  

  If the amount of information that is returned is significantly large, an identifier will also be returned, which can be used in a subsequent list deployments call to return the next set of deployments in the list.

  

  

