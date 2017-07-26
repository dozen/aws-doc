[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam list-groups:


***********
list-groups
***********



===========
Description
===========



Lists the groups that have the specified path prefix.

 

You can paginate the results using the ``MaxItems`` and ``Marker`` parameters. 



``list-groups`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Groups``


========
Synopsis
========

::

    list-groups
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


  The path prefix for filtering the results. For example, the prefix ``/division_abc/subdivision_xyz/`` gets all groups whose path starts with ``/division_abc/subdivision_xyz/`` . 

   

  This parameter is optional. If it is not included, it defaults to a slash (/), listing all groups. 

  

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

**To list the IAM groups for the current account**

The following ``list-groups`` command lists the IAM groups in the current account::

  aws iam list-groups

Output::

  "Groups": [
    {
        "Path": "/",
        "CreateDate": "2013-06-04T20:27:27.972Z",
        "GroupId": "AIDACKCEVSQ6C2EXAMPLE",
        "Arn": "arn:aws:iam::123456789012:group/Admins",
        "GroupName": "Admins"
    },
    {
        "Path": "/",
        "CreateDate": "2013-04-16T20:30:42Z",
        "GroupId": "AIDGPMS9RO4H3FEXAMPLE",
        "Arn": "arn:aws:iam::123456789012:group/S3-Admins",
        "GroupName": "S3-Admins"
    }
  ]

For more information, see `Creating and Listing Groups`_ in the *Using IAM* guide.

.. _`Creating and Listing Groups`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_CreatingAndListingGroups.html



======
Output
======

Groups -> (list)

  

  A list of groups.

  

  (structure)

    

    Contains information about an IAM group entity.

     

    This data type is used as a response element in the following actions:

     

     
    *  create-group  
     
    *  get-group  
     
    *  list-groups  
     

    

    Path -> (string)

      

      The path to the group. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

      

    GroupName -> (string)

      

      The friendly name that identifies the group.

      

      

    GroupId -> (string)

      

      The stable and unique string identifying the group. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

      

    Arn -> (string)

      

      The Amazon Resource Name (ARN) specifying the group. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

      

    CreateDate -> (timestamp)

      

      The date and time, in `ISO 8601 date-time format`_ , when the group was created.

      

      

    

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

  

  

Marker -> (string)

  

  When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

  

  



.. _ISO 8601 date-time format: http://www.iso.org/iso/iso8601
.. _IAM Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html
