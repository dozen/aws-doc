[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation delete-stack:


************
delete-stack
************



===========
Description
===========



Deletes a specified stack. Once the call completes successfully, stack deletion starts. Deleted stacks do not show up in the  describe-stacks API if the deletion has been completed successfully.



========
Synopsis
========

::

    delete-stack
  --stack-name <value>
  [--retain-resources <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stack-name`` (string)


  The name or the unique stack ID that is associated with the stack.

  

``--retain-resources`` (list)


  For stacks in the ``DELETE_FAILED`` state, a list of resource logical IDs that are associated with the resources you want to retain. During deletion, AWS CloudFormation deletes the stack but does not delete the retained resources.

   

  Retaining resources is useful when you cannot delete a resource, such as a non-empty S3 bucket, but you want to delete the stack.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None