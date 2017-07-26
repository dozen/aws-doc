[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam list-groups-for-user:


********************
list-groups-for-user
********************



===========
Description
===========



Lists the groups the specified user belongs to.

 

You can paginate the results using the ``MaxItems`` and ``Marker`` parameters. 



``list-groups-for-user`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Groups``


========
Synopsis
========

::

    list-groups-for-user
  --user-name <value>
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--user-name`` (string)


  The name of the user to list groups for.

  

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

**To list the groups that an IAM user belongs to**

The following ``list-groups-for-user`` command displays the groups that the IAM user named ``Bob`` belongs to::

  aws iam list-groups-for-user --user-name Bob

Output::

  "Groups": [
      {
          "Path": "/",
          "CreateDate": "2013-05-06T01:18:08Z",
          "GroupId": "AKIAIOSFODNN7EXAMPLE",
          "Arn": "arn:aws:iam::123456789012:group/Admin",
          "GroupName": "Admin"
      },
      {
          "Path": "/",
          "CreateDate": "2013-05-06T01:37:28Z",
          "GroupId": "AKIAI44QH8DHBEXAMPLE",
          "Arn": "arn:aws:iam::123456789012:group/s3-Users",
          "GroupName": "s3-Users"
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
