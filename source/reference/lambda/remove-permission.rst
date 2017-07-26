[ :ref:`aws <cli:aws>` . :ref:`lambda <cli:aws lambda>` ]

.. _cli:aws lambda remove-permission:


*****************
remove-permission
*****************



===========
Description
===========



You can remove individual permissions from an resource policy associated with a Lambda function by providing a statement ID that you provided when you added the permission. 

 

If you are using versioning, the permissions you remove are specific to the Lambda function version or alias you specify in the ``add-permission`` request via the ``qualifier`` parameter. For more information about versioning, see `AWS Lambda Function Versioning and Aliases`_ . 

 

Note that removal of a permission will cause an active event source to lose permission to the function. 

 

You need permission for the ``lambda:RemovePermission`` action.



========
Synopsis
========

::

    remove-permission
  --function-name <value>
  --statement-id <value>
  [--qualifier <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--function-name`` (string)


  Lambda function whose resource policy you want to remove a permission from.

   

  You can specify a function name (for example, ``Thumbnail`` ) or you can specify Amazon Resource Name (ARN) of the function (for example, ``arn:aws:lambda:us-west-2:account-id:function:ThumbNail`` ). AWS Lambda also allows you to specify a partial ARN (for example, ``account-id:Thumbnail`` ). Note that the length constraint applies only to the ARN. If you specify only the function name, it is limited to 64 character in length. 

  

``--statement-id`` (string)


  Statement ID of the permission to remove.

  

``--qualifier`` (string)


  You can specify this optional parameter to remove permission associated with a specific function version or function alias. If you don't specify this parameter, the API removes permission associated with the unqualified function ARN.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None

.. _AWS Lambda Function Versioning and Aliases: http://docs.aws.amazon.com/lambda/latest/dg/versioning-aliases.html
