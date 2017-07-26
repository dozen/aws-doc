[ :ref:`aws <cli:aws>` . :ref:`cloudhsm <cli:aws cloudhsm>` ]

.. _cli:aws cloudhsm list-tags-for-resource:


**********************
list-tags-for-resource
**********************



===========
Description
===========



Returns a list of all tags for the specified AWS CloudHSM resource.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudhsm-2014-05-30/ListTagsForResource>`_


========
Synopsis
========

::

    list-tags-for-resource
  --resource-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-arn`` (string)


  The Amazon Resource Name (ARN) of the AWS CloudHSM resource.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

TagList -> (list)

  

  One or more tags.

  

  (structure)

    

    A key-value pair that identifies or specifies metadata about an AWS CloudHSM resource.

    

    Key -> (string)

      

      The key of the tag.

      

      

    Value -> (string)

      

      The value of the tag.

      

      

    

  

