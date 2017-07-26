[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam list-access-keys:


****************
list-access-keys
****************



===========
Description
===========



Returns information about the access key IDs associated with the specified user. If there are none, the action returns an empty list. 

 

Although each user is limited to a small number of keys, you can still paginate the results using the ``MaxItems`` and ``Marker`` parameters. 

 

If the ``UserName`` field is not specified, the UserName is determined implicitly based on the AWS access key ID used to sign the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated users. 

 

.. note::

  To ensure the security of your AWS account, the secret access key is accessible only during key and user creation. 



``list-access-keys`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``AccessKeyMetadata``


========
Synopsis
========

::

    list-access-keys
  [--user-name <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--user-name`` (string)


  The name of the user.

  

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

**To list the access key IDs for an IAM user**

The following ``list-access-keys`` command lists the access keys IDs for the IAM user named ``Bob``::

  aws iam list-access-keys --user-name Bob

Output::

  "AccessKeyMetadata": [
      {
          "UserName": "Bob",
          "Status": "Active",
          "CreateDate": "2013-06-04T18:17:34Z",
          "AccessKeyId": "AKIAIOSFODNN7EXAMPLE"
      },
      {
          "UserName": "Bob",
          "Status": "Inactive",
          "CreateDate": "2013-06-06T20:42:26Z",
          "AccessKeyId": "AKIAI44QH8DHBEXAMPLE"
      }
  ]

You cannot list the secret access keys for IAM users. If the secret access keys are lost, you must create new access keys using the ``create-access-keys`` command.

For more information, see `Creating, Modifying, and Viewing User Security Credentials`_ in the *Using IAM* guide.

.. _`Creating, Modifying, and Viewing User Security Credentials`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_CreateAccessKey.html




======
Output
======

AccessKeyMetadata -> (list)

  

  A list of access key metadata.

  

  (structure)

    

    Contains information about an AWS access key, without its secret key.

     

    This data type is used as a response element in the  list-access-keys action.

    

    UserName -> (string)

      

      The name of the IAM user that the key is associated with.

      

      

    AccessKeyId -> (string)

      

      The ID for this access key.

      

      

    Status -> (string)

      

      The status of the access key. ``Active`` means the key is valid for API calls; ``Inactive`` means it is not.

      

      

    CreateDate -> (timestamp)

      

      The date when the access key was created.

      

      

    

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

  

  

Marker -> (string)

  

  When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

  

  

