[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models put-slot-type:


*************
put-slot-type
*************



===========
Description
===========



Creates a custom slot type or replaces an existing custom slot type.

 

To create a custom slot type, specify a name for the slot type and a set of enumeration values, which are the values that a slot of this type can assume. For more information, see  how-it-works .

 

If you specify the name of an existing slot type, the fields in the request replace the existing values in the ``$LATEST`` version of the slot type. Amazon Lex removes the fields that you don't provide in the request. If you don't specify required fields, Amazon Lex throws an exception.

 

This operation requires permissions for the ``lex:PutSlotType`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/PutSlotType>`_


========
Synopsis
========

::

    put-slot-type
  --name <value>
  [--description <value>]
  [--enumeration-values <value>]
  [--checksum <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the slot type. The name is *not* case sensitive. 

   

  The name can't match a built-in slot type name, or a built-in slot type name with "AMAZON." removed. For example, because there is a built-in slot type called ``AMAZON.DATE`` , you can't create a custom slot type called ``DATE`` .

   

  For a list of built-in slot types, see `Slot Type Reference <https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/built-in-intent-ref/slot-type-reference>`_ in the *Alexa Skills Kit* .

  

``--description`` (string)


  A description of the slot type.

  

``--enumeration-values`` (list)


  A list of ``EnumerationValue`` objects that defines the values that the slot type can take.

  



Shorthand Syntax::

    value=string ...




JSON Syntax::

  [
    {
      "value": "string"
    }
    ...
  ]



``--checksum`` (string)


  Identifies a specific revision of the ``$LATEST`` version.

   

  When you create a new slot type, leave the ``checksum`` field blank. If you specify a checksum you get a ``BadRequestException`` exception.

   

  When you want to update a slot type, set the ``checksum`` field to the checksum of the most recent revision of the ``$LATEST`` version. If you don't specify the ``checksum`` field, or if the checksum does not match the ``$LATEST`` version, you get a ``PreconditionFailedException`` exception.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

name -> (string)

  

  The name of the slot type.

  

  

description -> (string)

  

  A description of the slot type.

  

  

enumerationValues -> (list)

  

  A list of ``EnumerationValue`` objects that defines the values that the slot type can take.

  

  (structure)

    

    Each slot type can have a set of values. Each enumeration value represents a value the slot type can take. 

     

    For example, a pizza ordering bot could have a slot type that specifies the type of crust that the pizza should have. The slot type could include the values 

     

     
    * thick 
     
    * thin 
     
    * stuffed 
     

    

    value -> (string)

      

      The value of the slot type.

      

      

    

  

lastUpdatedDate -> (timestamp)

  

  The date that the slot type was updated. When you create a slot type, the creation date and last update date are the same.

  

  

createdDate -> (timestamp)

  

  The date that the slot type was created.

  

  

version -> (string)

  

  The version of the slot type. For a new slot type, the version is always ``$LATEST`` . 

  

  

checksum -> (string)

  

  Checksum of the ``$LATEST`` version of the slot type.

  

  

