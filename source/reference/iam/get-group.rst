[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-group:


*********
get-group
*********



===========
Description
===========



Returns a list of users that are in the specified group. You can paginate the results using the ``MaxItems`` and ``Marker`` parameters. 



``get-group`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Users``


========
Synopsis
========

::

    get-group
  --group-name <value>
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--group-name`` (string)


  The name of the group.

  

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

**To get an IAM group**

This example returns details about the IAM group ``Admins``::

  aws iam get-group --group-name Admins

Output::

  {
      "Group": {
          "Path": "/",
          "CreateDate": "2015-06-16T19:41:48Z",
          "GroupId": "AIDGPMS9RO4H3FEXAMPLE",
          "Arn": "arn:aws:iam::123456789012:group/Admins",
          "GroupName": "Admins"
      },
	  "Users": []
  }

For more information, see `IAM Users and Groups`_ in the *Using IAM* guide.

.. _`IAM Users and Groups`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_WorkingWithGroupsAndUsers.html

======
Output
======

Group -> (structure)

  

  Information about the group.

  

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

    

    

  

Users -> (list)

  

  A list of users in the group.

  

  (structure)

    

    Contains information about an IAM user entity.

     

    This data type is used as a response element in the following actions:

     

     
    *  create-user   
     
    *  get-user   
     
    *  list-users   
     

    

    Path -> (string)

      

      The path to the user. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

      

      

    UserName -> (string)

      

      The friendly name identifying the user.

      

      

    UserId -> (string)

      

      The stable and unique string identifying the user. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

      

      

    Arn -> (string)

      

      The Amazon Resource Name (ARN) that identifies the user. For more information about ARNs and how to use ARNs in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

      

    CreateDate -> (timestamp)

      

      The date and time, in `ISO 8601 date-time format`_ , when the user was created.

      

      

    PasswordLastUsed -> (timestamp)

      

      The date and time, in `ISO 8601 date-time format`_ , when the user's password was last used to sign in to an AWS website. For a list of AWS websites that capture a user's last sign-in time, see the `Credential Reports`_ topic in the *Using IAM* guide. If a password is used more than once in a five-minute span, only the first use is returned in this field. This field is null (not present) when:

       

       
      * The user does not have a password 
       
      * The password exists but has never been used (at least not since IAM started tracking this information on October 20th, 2014 
       
      * there is no sign-in data associated with the user 
       

       

      This value is returned only in the  get-user and  list-users actions. 

      

      

    

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

  

  

Marker -> (string)

  

  When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

  

  



.. _ISO 8601 date-time format: http://www.iso.org/iso/iso8601
.. _Credential Reports: http://docs.aws.amazon.com/IAM/latest/UserGuide/credential-reports.html
.. _IAM Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html
