[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks describe-ecs-clusters:


*********************
describe-ecs-clusters
*********************



===========
Description
===========



Describes Amazon ECS clusters that are registered with a stack. If you specify only a stack ID, you can use the ``MaxResults`` and ``NextToken`` parameters to paginate the response. However, AWS OpsWorks Stacks currently supports only one cluster per layer, so the result set has a maximum of one element.

 

 **Required Permissions** : To use this action, an IAM user must have a Show, Deploy, or Manage permissions level for the stack or an attached policy that explicitly grants permission. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .

 

This call accepts only one resource-identifying parameter.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/DescribeEcsClusters>`_


``describe-ecs-clusters`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``EcsClusters``


========
Synopsis
========

::

    describe-ecs-clusters
  [--ecs-cluster-arns <value>]
  [--stack-id <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--ecs-cluster-arns`` (list)


  A list of ARNs, one for each cluster to be described.

  



Syntax::

  "string" "string" ...



``--stack-id`` (string)


  A stack ID. ``describe-ecs-clusters`` returns a description of the cluster that is registered with the stack.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

EcsClusters -> (list)

  

  A list of ``EcsCluster`` objects containing the cluster descriptions.

  

  (structure)

    

    Describes a registered Amazon ECS cluster.

    

    EcsClusterArn -> (string)

      

      The cluster's ARN.

      

      

    EcsClusterName -> (string)

      

      The cluster name.

      

      

    StackId -> (string)

      

      The stack ID.

      

      

    RegisteredAt -> (string)

      

      The time and date that the cluster was registered with the stack.

      

      

    

  

NextToken -> (string)

  

  If a paginated request does not return all of the remaining results, this parameter is set to a token that you can assign to the request object's ``NextToken`` parameter to retrieve the next set of results. If the previous paginated request returned all of the remaining results, this parameter is set to ``null`` .

  

  

