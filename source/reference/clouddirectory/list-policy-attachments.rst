[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory list-policy-attachments:


***********************
list-policy-attachments
***********************



===========
Description
===========



Returns all of the ``ObjectIdentifiers`` to which a given policy is attached.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/ListPolicyAttachments>`_


========
Synopsis
========

::

    list-policy-attachments
  --directory-arn <value>
  --policy-reference <value>
  [--next-token <value>]
  [--max-results <value>]
  [--consistency-level <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-arn`` (string)


  The Amazon Resource Name (ARN) that is associated with the  Directory where objects reside. For more information, see  arns .

  

``--policy-reference`` (structure)


  The reference that identifies the policy object.

  



Shorthand Syntax::

    Selector=string




JSON Syntax::

  {
    "Selector": "string"
  }



``--next-token`` (string)


  The pagination token.

  

``--max-results`` (integer)


  The maximum number of items to be retrieved in a single call. This is an approximate number.

  

``--consistency-level`` (string)


  Represents the manner and timing in which the successful write or update of an object is reflected in a subsequent read operation of that same object.

  

  Possible values:

  
  *   ``SERIALIZABLE``

  
  *   ``EVENTUAL``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ObjectIdentifiers -> (list)

  

  A list of ``ObjectIdentifiers`` to which the policy is attached.

  

  (string)

    

    

  

NextToken -> (string)

  

  The pagination token.

  

  

