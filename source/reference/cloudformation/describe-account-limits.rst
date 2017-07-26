[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation describe-account-limits:


***********************
describe-account-limits
***********************



===========
Description
===========



Retrieves your account's AWS CloudFormation limits, such as the maximum number of stacks that you can create in your account.



========
Synopsis
========

::

    describe-account-limits
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--next-token`` (string)


  A string that identifies the next page of limits that you want to retrieve.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

AccountLimits -> (list)

  

  An account limit structure that contain a list of AWS CloudFormation account limits and their values.

  

  (structure)

    

    The AccountLimit data type.

    

    Name -> (string)

      

      The name of the account limit. Currently, the only account limit is ``StackLimit`` .

      

      

    Value -> (integer)

      

      The value that is associated with the account limit name.

      

      

    

  

NextToken -> (string)

  

  If the output exceeds 1 MB in size, a string that identifies the next page of limits. If no additional page exists, this value is null.

  

  

