[ :ref:`aws <cli:aws>` . :ref:`shield <cli:aws shield>` ]

.. _cli:aws shield list-protections:


****************
list-protections
****************



===========
Description
===========



Lists all  Protection objects for the account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/shield-2016-06-02/ListProtections>`_


========
Synopsis
========

::

    list-protections
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--next-token`` (string)


  The ``ListProtectionsRequest.NextToken`` value from a previous call to ``list-protections`` . Pass null if this is the first call.

  

``--max-results`` (integer)


  The maximum number of  Protection objects to be returned. If this is left blank the first 20 results will be returned.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Protections -> (list)

  

  The array of enabled  Protection objects.

  

  (structure)

    

    An object that represents a resource that is under DDoS protection.

    

    Id -> (string)

      

      The unique identifier (ID) of the protection.

      

      

    Name -> (string)

      

      The friendly name of the protection. For example, ``My CloudFront distributions`` .

      

      

    ResourceArn -> (string)

      

      The ARN (Amazon Resource Name) of the AWS resource that is protected.

      

      

    

  

NextToken -> (string)

  

  If you specify a value for ``max-results`` and you have more Protections than the value of MaxResults, AWS Shield Advanced returns a NextToken value in the response that allows you to list another group of Protections. For the second and subsequent list-protections requests, specify the value of NextToken from the previous response to get information about another batch of Protections.

  

  

