[ :ref:`aws <cli:aws>` . :ref:`cloudfront <cli:aws cloudfront>` ]

.. _cli:aws cloudfront list-tags-for-resource:


**********************
list-tags-for-resource
**********************



===========
Description
===========



List tags for a CloudFront resource.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudfront-2017-03-25/ListTagsForResource>`_


.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.cloudfront true`` 



========
Synopsis
========

::

    list-tags-for-resource
  --resource <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource`` (string)


  An ARN of a CloudFront resource.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Tags -> (structure)

  

  A complex type that contains zero or more ``Tag`` elements.

  

  Items -> (list)

    

    A complex type that contains ``Tag`` elements.

    

    (structure)

      

      A complex type that contains ``Tag`` key and ``Tag`` value.

      

      Key -> (string)

        

        A string that contains ``Tag`` key.

         

        The string length should be between 1 and 128 characters. Valid characters include ``a-z`` , ``A-Z`` , ``0-9`` , space, and the special characters ``_ - . : / = + @`` .

        

        

      Value -> (string)

        

        A string that contains an optional ``Tag`` value.

         

        The string length should be between 0 and 256 characters. Valid characters include ``a-z`` , ``A-Z`` , ``0-9`` , space, and the special characters ``_ - . : / = + @`` .

        

        

      

    

  

