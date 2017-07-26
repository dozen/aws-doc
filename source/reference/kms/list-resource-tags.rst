[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms list-resource-tags:


******************
list-resource-tags
******************



===========
Description
===========



Returns a list of all tags for the specified customer master key (CMK).



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kms-2014-11-01/ListResourceTags>`_


========
Synopsis
========

::

    list-resource-tags
  --key-id <value>
  [--limit <value>]
  [--marker <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--key-id`` (string)


  A unique identifier for the CMK whose tags you are listing. You can use the unique key ID or the Amazon Resource Name (ARN) of the CMK. Examples:

   

   
  * Unique key ID: ``1234abcd-12ab-34cd-56ef-1234567890ab``   
   
  * Key ARN: ``arn:aws:kms:us-east-2:111122223333:key/1234abcd-12ab-34cd-56ef-1234567890ab``   
   

  

``--limit`` (integer)


  Use this parameter to specify the maximum number of items to return. When this value is present, AWS KMS does not return more than the specified number of items, but it might return fewer.

   

  This value is optional. If you include a value, it must be between 1 and 50, inclusive. If you do not include a value, it defaults to 50.

  

``--marker`` (string)


  Use this parameter in a subsequent request after you receive a response with truncated results. Set it to the value of ``NextMarker`` from the truncated response you just received.

   

  Do not attempt to construct this value. Use only the value of ``NextMarker`` from the truncated response you just received.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Tags -> (list)

  

  A list of tags. Each tag consists of a tag key and a tag value.

  

  (structure)

    

    A key-value pair. A tag consists of a tag key and a tag value. Tag keys and tag values are both required, but tag values can be empty (null) strings.

    

    TagKey -> (string)

      

      The key of the tag.

      

      

    TagValue -> (string)

      

      The value of the tag.

      

      

    

  

NextMarker -> (string)

  

  When ``Truncated`` is true, this element is present and contains the value to use for the ``Marker`` parameter in a subsequent request.

   

  Do not assume or infer any information from this value.

  

  

Truncated -> (boolean)

  

  A flag that indicates whether there are more items in the list. When this value is true, the list in this response is truncated. To retrieve more items, pass the value of the ``NextMarker`` element in this response to the ``Marker`` parameter in a subsequent request.

  

  

