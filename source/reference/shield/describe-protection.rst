[ :ref:`aws <cli:aws>` . :ref:`shield <cli:aws shield>` ]

.. _cli:aws shield describe-protection:


*******************
describe-protection
*******************



===========
Description
===========



Lists the details of a  Protection object.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/shield-2016-06-02/DescribeProtection>`_


========
Synopsis
========

::

    describe-protection
  --protection-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--protection-id`` (string)


  The unique identifier (ID) for the  Protection object that is described.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Protection -> (structure)

  

  The  Protection object that is described.

  

  Id -> (string)

    

    The unique identifier (ID) of the protection.

    

    

  Name -> (string)

    

    The friendly name of the protection. For example, ``My CloudFront distributions`` .

    

    

  ResourceArn -> (string)

    

    The ARN (Amazon Resource Name) of the AWS resource that is protected.

    

    

  

