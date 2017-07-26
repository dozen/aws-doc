[ :ref:`aws <cli:aws>` . :ref:`lambda <cli:aws lambda>` ]

.. _cli:aws lambda add-permission:


**************
add-permission
**************



===========
Description
===========



Adds a permission to the resource policy associated with the specified AWS Lambda function. You use resource policies to grant permissions to event sources that use *push* model. In a *push* model, event sources (such as Amazon S3 and custom applications) invoke your Lambda function. Each permission you add to the resource policy allows an event source, permission to invoke the Lambda function. 

 

For information about the push model, see `AWS Lambda\: How it Works`_ . 

 

If you are using versioning, the permissions you add are specific to the Lambda function version or alias you specify in the ``add-permission`` request via the ``qualifier`` parameter. For more information about versioning, see `AWS Lambda Function Versioning and Aliases`_ . 

 

This operation requires permission for the ``lambda:AddPermission`` action.



========
Synopsis
========

::

    add-permission
  --function-name <value>
  --statement-id <value>
  --action <value>
  --principal <value>
  [--source-arn <value>]
  [--source-account <value>]
  [--qualifier <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--function-name`` (string)


  Name of the Lambda function whose resource policy you are updating by adding a new permission.

   

  You can specify a function name (for example, ``Thumbnail`` ) or you can specify Amazon Resource Name (ARN) of the function (for example, ``arn:aws:lambda:us-west-2:account-id:function:ThumbNail`` ). AWS Lambda also allows you to specify partial ARN (for example, ``account-id:Thumbnail`` ). Note that the length constraint applies only to the ARN. If you specify only the function name, it is limited to 64 character in length. 

  

``--statement-id`` (string)


  A unique statement identifier.

  

``--action`` (string)


  The AWS Lambda action you want to allow in this statement. Each Lambda action is a string starting with ``lambda:`` followed by the API name (see  Operations ). For example, ``lambda:CreateFunction`` . You can use wildcard (``lambda:*`` ) to grant permission for all AWS Lambda actions. 

  

``--principal`` (string)


  The principal who is getting this permission. It can be Amazon S3 service principal (``s3.amazonaws.com`` ) if you want Amazon S3 to invoke the function, an AWS account ID if you are granting cross-account permission, or any valid AWS service principal such as ``sns.amazonaws.com`` . For example, you might want to allow a custom application in another AWS account to push events to AWS Lambda by invoking your function. 

  

``--source-arn`` (string)


  This is optional; however, when granting Amazon S3 permission to invoke your function, you should specify this field with the bucket Amazon Resource Name (ARN) as its value. This ensures that only events generated from the specified bucket can invoke the function. 

   

  .. warning::

    If you add a permission for the Amazon S3 principal without providing the source ARN, any AWS account that creates a mapping to your function ARN can send events to invoke your Lambda function from Amazon S3.

  

``--source-account`` (string)


  The AWS account ID (without a hyphen) of the source owner. For example, if the ``SourceArn`` identifies a bucket, then this is the bucket owner's account ID. You can use this additional condition to ensure the bucket you specify is owned by a specific account (it is possible the bucket owner deleted the bucket and some other AWS account created the bucket). You can also use this condition to specify all sources (that is, you don't specify the ``SourceArn`` ) owned by a specific account. 

  

``--qualifier`` (string)


  You can use this optional query parameter to describe a qualified ARN using a function version or an alias name. The permission will then apply to the specific qualified ARN. For example, if you specify function version 2 as the qualifier, then permission applies only when request is made using qualified function ARN: 

   

  ``arn:aws:lambda:aws-region:acct-id:function:function-name:2`` 

   

  If you specify an alias name, for example ``PROD`` , then the permission is valid only for requests made using the alias ARN:

   

  ``arn:aws:lambda:aws-region:acct-id:function:function-name:PROD`` 

   

  If the qualifier is not specified, the permission is valid only when requests is made using unqualified function ARN. 

   

  ``arn:aws:lambda:aws-region:acct-id:function:function-name`` 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Statement -> (string)

  

  The permission statement you specified in the request. The response returns the same as a string using a backslash ("\") as an escape character in the JSON. 

  

  



.. _AWS Lambda\: How it Works: http://docs.aws.amazon.com/lambda/latest/dg/lambda-introduction.html
.. _AWS Lambda Function Versioning and Aliases: http://docs.aws.amazon.com/lambda/latest/dg/versioning-aliases.html
