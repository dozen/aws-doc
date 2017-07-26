[ :ref:`aws <cli:aws>` . :ref:`servicecatalog <cli:aws servicecatalog>` ]

.. _cli:aws servicecatalog describe-constraint:


*******************
describe-constraint
*******************



===========
Description
===========



Retrieves detailed information for a specified constraint.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/servicecatalog-2015-12-10/DescribeConstraint>`_


========
Synopsis
========

::

    describe-constraint
  [--accept-language <value>]
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--accept-language`` (string)


  The language code to use for this operation. Supported language codes are as follows:

   

  "en" (English)

   

  "jp" (Japanese)

   

  "zh" (Chinese)

   

  If no code is specified, "en" is used as the default.

  

``--id`` (string)


  The identifier of the constraint.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ConstraintDetail -> (structure)

  

  Detailed constraint information.

  

  ConstraintId -> (string)

    

    The identifier of the constraint.

    

    

  Type -> (string)

    

    The type of the constraint.

    

    

  Description -> (string)

    

    The text description of the constraint.

    

    

  Owner -> (string)

    

    The owner of the constraint.

    

    

  

ConstraintParameters -> (string)

  

  The current parameters associated with the specified constraint.

  

  

Status -> (string)

  

  The status of the current request.

  

  

