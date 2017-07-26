[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam list-roles:


**********
list-roles
**********



===========
Description
===========



Lists the roles that have the specified path prefix. If there are none, the action returns an empty list. For more information about roles, go to `Working with Roles`_ . 

 

You can paginate the results using the ``MaxItems`` and ``Marker`` parameters. 



``list-roles`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Roles``


========
Synopsis
========

::

    list-roles
  [--path-prefix <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--path-prefix`` (string)


  The path prefix for filtering the results. For example, the prefix ``/application_abc/component_xyz/`` gets all roles whose path starts with ``/application_abc/component_xyz/`` . 

   

  This parameter is optional. If it is not included, it defaults to a slash (/), listing all roles. 

  

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

**To list IAM roles for the current account**

The following ``list-roles`` command lists IAM roles for the current account::

  aws iam list-roles

Output::

  {
    "Roles": [
      {
        "AssumeRolePolicyDocument": {
          "Version": "2012-10-17",
          "Statement": [
            {
              "Action": "sts:AssumeRole",
              "Principal": {
                "Service": "ec2.amazonaws.com"
              },
              "Effect": "Allow",
              "Sid": ""
            }
          ]
        },
        "RoleId": "AROAJ52OTH4H7LEXAMPLE",
        "CreateDate": "2013-05-11T00:02:27Z",
        "RoleName": "ExampleRole1",
        "Path": "/",
        "Arn": "arn:aws:iam::123456789012:role/ExampleRole1"
      },
      {
        "AssumeRolePolicyDocument": {
          "Version": "2012-10-17",
          "Statement": [
            {
              "Action": "sts:AssumeRole",
              "Principal": {
                "Service": "elastictranscoder.amazonaws.com"
              },
              "Effect": "Allow",
              "Sid": ""
            }
          ]
        },
        "RoleId": "AROAI4QRP7UFT7EXAMPLE",
        "CreateDate": "2013-04-18T05:01:58Z",
        "RoleName": "emr-access",
        "Path": "/",
        "Arn": "arn:aws:iam::123456789012:role/emr-access"
      }
    ]
  }

For more information, see `Creating a Role`_ in the *Using IAM* guide.

.. _`Creating a Role`: http://docs.aws.amazon.com/IAM/latest/UserGuide/creating-role.html



======
Output
======

Roles -> (list)

  

  A list of roles.

  

  (structure)

    

    Contains information about an IAM role.

     

    This data type is used as a response element in the following actions:

     

     
    *  create-role   
     
    *  get-role   
     
    *  list-roles   
     

    

    Path -> (string)

      

      The path to the role. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

      

    RoleName -> (string)

      

      The friendly name that identifies the role.

      

      

    RoleId -> (string)

      

      The stable and unique string identifying the role. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

      

    Arn -> (string)

      

      The Amazon Resource Name (ARN) specifying the role. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

      

    CreateDate -> (timestamp)

      

      The date and time, in `ISO 8601 date-time format`_ , when the role was created.

      

      

    AssumeRolePolicyDocument -> (string)

      

      The policy that grants an entity permission to assume the role.

      

      

    

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

  

  

Marker -> (string)

  

  When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

  

  



.. _ISO 8601 date-time format: http://www.iso.org/iso/iso8601
.. _Working with Roles: http://docs.aws.amazon.com/IAM/latest/UserGuide/WorkingWithRoles.html
.. _IAM Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html
