[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam list-entities-for-policy:


************************
list-entities-for-policy
************************



===========
Description
===========



Lists all users, groups, and roles that the specified managed policy is attached to. 

 

You can use the optional ``EntityFilter`` parameter to limit the results to a particular type of entity (users, groups, or roles). For example, to list only the roles that are attached to the specified policy, set ``EntityFilter`` to ``Role`` . 

 

You can paginate the results using the ``MaxItems`` and ``Marker`` parameters. 



``list-entities-for-policy`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``PolicyGroups``, ``PolicyUsers``, ``PolicyRoles``


========
Synopsis
========

::

    list-entities-for-policy
  --policy-arn <value>
  [--entity-filter <value>]
  [--path-prefix <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--policy-arn`` (string)


  The Amazon Resource Name (ARN). ARNs are unique identifiers for AWS resources. 

   

  For more information about ARNs, go to `Amazon Resource Names (ARNs) and AWS Service Namespaces`_ in the *AWS General Reference* . 

  

``--entity-filter`` (string)


  The entity type to use for filtering the results. 

   

  For example, when ``EntityFilter`` is ``Role`` , only the roles that are attached to the specified policy are returned. This parameter is optional. If it is not included, all attached entities (users, groups, and roles) are returned. 

  

  Possible values:

  
  *   ``User``

  
  *   ``Role``

  
  *   ``Group``

  
  *   ``LocalManagedPolicy``

  
  *   ``AWSManagedPolicy``

  

  

``--path-prefix`` (string)


  The path prefix for filtering the results. This parameter is optional. If it is not included, it defaults to a slash (/), listing all entities.

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To list all users, groups, and roles that the specified managed policy is attached to**

This example returns a list of IAM groups, roles, and users who have the policy ``arn:aws:iam::123456789012:policy/TestPolicy`` attached::

  aws iam list-entities-for-policy --policy-arn arn:aws:iam::123456789012:policy/TestPolicy 

Output::

  {
    "PolicyGroups": [
      {
        "GroupName": "Admins"
      }
    ],
    "PolicyUsers": [
      {
        "UserName": "Bob"
      }
    ],
    "PolicyRoles": [
      {
        "RoleName": "testRole"
      }
    ],
    "IsTruncated": false
  }

For more information, see `Overview of IAM Policies`_ in the *Using IAM* guide.

.. _`Overview of IAM Policies`: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies_overview.html

======
Output
======

PolicyGroups -> (list)

  

  A list of groups that the policy is attached to.

  

  (structure)

    

    Contains information about a group that a managed policy is attached to.

     

    This data type is used as a response element in the  list-entities-for-policy action. 

     

    For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

    

    GroupName -> (string)

      

      The name (friendly name, not ARN) identifying the group.

      

      

    

  

PolicyUsers -> (list)

  

  A list of users that the policy is attached to.

  

  (structure)

    

    Contains information about a user that a managed policy is attached to.

     

    This data type is used as a response element in the  list-entities-for-policy action. 

     

    For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

    

    UserName -> (string)

      

      The name (friendly name, not ARN) identifying the user.

      

      

    

  

PolicyRoles -> (list)

  

  A list of roles that the policy is attached to.

  

  (structure)

    

    Contains information about a role that a managed policy is attached to.

     

    This data type is used as a response element in the  list-entities-for-policy action. 

     

    For more information about managed policies, refer to `Managed Policies and Inline Policies`_ in the *Using IAM* guide. 

    

    RoleName -> (string)

      

      The name (friendly name, not ARN) identifying the role.

      

      

    

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

  

  

Marker -> (string)

  

  When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

  

  



.. _Amazon Resource Names (ARNs) and AWS Service Namespaces: http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html
.. _Managed Policies and Inline Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/policies-managed-vs-inline.html
