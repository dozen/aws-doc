[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam list-users:


**********
list-users
**********



===========
Description
===========



Lists the IAM users that have the specified path prefix. If no path prefix is specified, the action returns all users in the AWS account. If there are none, the action returns an empty list. 

 

You can paginate the results using the ``MaxItems`` and ``Marker`` parameters. 



``list-users`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Users``


========
Synopsis
========

::

    list-users
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


  The path prefix for filtering the results. For example: ``/division_abc/subdivision_xyz/`` , which would get all user names whose path starts with ``/division_abc/subdivision_xyz/`` . 

   

  This parameter is optional. If it is not included, it defaults to a slash (/), listing all user names. 

  

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

**To list IAM users**

The following ``list-users`` command lists the IAM users in the current account::

  aws iam list-users

Output::

  "Users": [
      {
          "UserName": "Adele",
          "Path": "/",
          "CreateDate": "2013-03-07T05:14:48Z",
          "UserId": "AKIAI44QH8DHBEXAMPLE",
          "Arn": "arn:aws:iam::123456789012:user/Adele"
      },
      {
          "UserName": "Bob",
          "Path": "/",
          "CreateDate": "2012-09-21T23:03:13Z",
          "UserId": "AKIAIOSFODNN7EXAMPLE",
          "Arn": "arn:aws:iam::123456789012:user/Bob"
      }
  ]

For more information, see `Listing Users`_ in the *Using IAM* guide.

.. _`Listing Users`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_GetListOfUsers.html



======
Output
======

Users -> (list)

  

  A list of users.

  

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
