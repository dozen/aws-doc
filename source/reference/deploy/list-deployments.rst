[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy list-deployments:


****************
list-deployments
****************



===========
Description
===========



Lists the deployments in a deployment group for an application registered with the applicable IAM user or AWS account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/ListDeployments>`_


``list-deployments`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``deployments``


========
Synopsis
========

::

    list-deployments
  [--application-name <value>]
  [--deployment-group-name <value>]
  [--include-only-statuses <value>]
  [--create-time-range <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The name of an AWS CodeDeploy application associated with the applicable IAM user or AWS account.

  

``--deployment-group-name`` (string)


  The name of an existing deployment group for the specified application.

  

``--include-only-statuses`` (list)


  A subset of deployments to list by status:

   

   
  * Created: Include created deployments in the resulting list. 
   
  * Queued: Include queued deployments in the resulting list. 
   
  * In Progress: Include in-progress deployments in the resulting list. 
   
  * Succeeded: Include successful deployments in the resulting list. 
   
  * Failed: Include failed deployments in the resulting list. 
   
  * Stopped: Include stopped deployments in the resulting list. 
   

  



Syntax::

  "string" "string" ...

  Where valid values are:
    Created
    Queued
    InProgress
    Succeeded
    Failed
    Stopped
    Ready





``--create-time-range`` (structure)


  A time range (start and end) for returning a subset of the list of deployments.

  



Shorthand Syntax::

    start=timestamp,end=timestamp




JSON Syntax::

  {
    "start": timestamp,
    "end": timestamp
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``next-token`` is provided in the command's output. To resume pagination, provide the ``next-token`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``next-token`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  If a large amount of information is returned, an identifier is also returned. It can be used in a subsequent list deployments call to return the next set of deployments in the list.

  

  

