[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks describe-ecs-clusters:


*********************
describe-ecs-clusters
*********************



===========
Description
===========



Describes Amazon ECS clusters that are registered with a stack. If you specify only a stack ID, you can use the ``MaxResults`` and ``NextToken`` parameters to paginate the response. However, AWS OpsWorks currently supports only one cluster per layer, so the result set has a maximum of one element.

 

**Required Permissions** : To use this action, an IAM user must have a Show, Deploy, or Manage permissions level for the stack or an attached policy that explicitly grants permission. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    describe-ecs-clusters
  [--ecs-cluster-arns <value>]
  [--stack-id <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--ecs-cluster-arns`` (list)


  A list of ARNs, one for each cluster to be described.

  



Syntax::

  "string" "string" ...



``--stack-id`` (string)


  A stack ID. ``describe-ecs-clusters`` returns a description of the cluster that is registered with the stack.

  

``--next-token`` (string)


  If the previous paginated request did not return all of the remaining results, the response object's``NextToken`` parameter value is set to a token. To retrieve the next set of results, call ``describe-ecs-clusters`` again and assign that token to the request object's ``NextToken`` parameter. If there are no remaining results, the previous response object's ``NextToken`` parameter is set to ``null`` .

  

``--max-results`` (integer)


  To receive a paginated response, use this parameter to specify the maximum number of results to be returned with a single call. If the number of available results exceeds this maximum, the response includes a ``NextToken`` value that you can assign to the ``NextToken`` request parameter to get the next set of results.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  



.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
