[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy list-deployment-groups:


**********************
list-deployment-groups
**********************



===========
Description
===========



Lists the deployment groups for an application registered with the applicable IAM user or AWS account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/ListDeploymentGroups>`_


``list-deployment-groups`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``deploymentGroups``


========
Synopsis
========

::

    list-deployment-groups
  --application-name <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The name of an AWS CodeDeploy application associated with the applicable IAM user or AWS account.

  

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

  

  If a large amount of information is returned, an identifier is also returned. It can be used in a subsequent list deployment groups call to return the next set of deployment groups in the list.

  

  

