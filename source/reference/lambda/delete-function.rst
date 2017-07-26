[ :ref:`aws <cli:aws>` . :ref:`lambda <cli:aws lambda>` ]

.. _cli:aws lambda delete-function:


***************
delete-function
***************



===========
Description
===========



Deletes the specified Lambda function code and configuration.

 

If you are using the versioning feature and you don't specify a function version in your ``delete-function`` request, AWS Lambda will delete the function, including all its versions, and any aliases pointing to the function versions. To delete a specific function version, you must provide the function version via the ``qualifier`` parameter. For information about function versioning, see `AWS Lambda Function Versioning and Aliases`_ . 

 

When you delete a function the associated resource policy is also deleted. You will need to delete the event source mappings explicitly.

 

This operation requires permission for the ``lambda:DeleteFunction`` action.



========
Synopsis
========

::

    delete-function
  --function-name <value>
  [--qualifier <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--function-name`` (string)


  The Lambda function to delete.

   

  You can specify the function name (for example, ``Thumbnail`` ) or you can specify Amazon Resource Name (ARN) of the function (for example, ``arn:aws:lambda:us-west-2:account-id:function:ThumbNail`` ). If you are using versioning, you can also provide a qualified function ARN (ARN that is qualified with function version or alias name as suffix). AWS Lambda also allows you to specify only the function name with the account ID qualifier (for example, ``account-id:Thumbnail`` ). Note that the length constraint applies only to the ARN. If you specify only the function name, it is limited to 64 character in length. 

  

``--qualifier`` (string)


  Using this optional parameter you can specify a function version (but not the ``$LATEST`` version) to direct AWS Lambda to delete a specific function version. If the function version has one or more aliases pointing to it, you will get an error because you cannot have aliases pointing to it. You can delete any function version but not the ``$LATEST`` , that is, you cannot specify ``$LATEST`` as the value of this parameter. The ``$LATEST`` version can be deleted only when you want to delete all the function versions and aliases.

   

  You can only specify a function version, not an alias name, using this parameter. You cannot delete a function version using its alias.

   

  If you don't specify this parameter, AWS Lambda will delete the function, including all of its versions and aliases.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None

.. _AWS Lambda Function Versioning and Aliases: http://docs.aws.amazon.com/lambda/latest/dg/versioning-aliases.html
