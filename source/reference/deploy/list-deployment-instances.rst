[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy list-deployment-instances:


*************************
list-deployment-instances
*************************



===========
Description
===========



Lists the instance for a deployment associated with the applicable IAM user or AWS account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/ListDeploymentInstances>`_


``list-deployment-instances`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``instancesList``


========
Synopsis
========

::

    list-deployment-instances
  --deployment-id <value>
  [--instance-status-filter <value>]
  [--instance-type-filter <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--deployment-id`` (string)


  The unique ID of a deployment.

  

``--instance-status-filter`` (list)


  A subset of instances to list by status:

   

   
  * Pending: Include those instance with pending deployments. 
   
  * InProgress: Include those instance where deployments are still in progress. 
   
  * Succeeded: Include those instances with successful deployments. 
   
  * Failed: Include those instance with failed deployments. 
   
  * Skipped: Include those instance with skipped deployments. 
   
  * Unknown: Include those instance with deployments in an unknown state. 
   

  



Syntax::

  "string" "string" ...

  Where valid values are:
    Pending
    InProgress
    Succeeded
    Failed
    Skipped
    Unknown
    Ready





``--instance-type-filter`` (list)


  The set of instances in a blue/green deployment, either those in the original environment ("BLUE") or those in the replacement environment ("GREEN"), for which you want to view instance information.

  



Syntax::

  "string" "string" ...

  Where valid values are:
    Blue
    Green





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

  

  A list of instance IDs.

  

  (string)

    

    

  

nextToken -> (string)

  

  If a large amount of information is returned, an identifier is also returned. It can be used in a subsequent list deployment instances call to return the next set of deployment instances in the list.

  

  

