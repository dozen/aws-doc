[ :ref:`aws <cli:aws>` . :ref:`servicecatalog <cli:aws servicecatalog>` ]

.. _cli:aws servicecatalog describe-tag-option:


*******************
describe-tag-option
*******************



===========
Description
===========



Describes a TagOption.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/servicecatalog-2015-12-10/DescribeTagOption>`_


========
Synopsis
========

::

    describe-tag-option
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--id`` (string)


  The identifier of the TagOption.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

TagOptionDetail -> (structure)

  

  The resulting detailed TagOption information.

  

  Key -> (string)

    

    The TagOptionDetail key.

    

    

  Value -> (string)

    

    The TagOptionDetail value.

    

    

  Active -> (boolean)

    

    The TagOptionDetail active state.

    

    

  Id -> (string)

    

    The TagOptionDetail identifier.

    

    

  

