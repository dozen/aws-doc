[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models create-slot-type-version:


************************
create-slot-type-version
************************



===========
Description
===========



Creates a new version of a slot type based on the ``$LATEST`` version of the specified slot type. If the ``$LATEST`` version of this resource has not changed since the last version that you created, Amazon Lex doesn't create a new version. It returns the last version that you created. 

 

.. note::

   

  You can update only the ``$LATEST`` version of a slot type. You can't update the numbered versions that you create with the ``create-slot-type-version`` operation.

   

 

When you create a version of a slot type, Amazon Lex sets the version to 1. Subsequent versions increment by 1. For more information, see  versioning-intro . 

 

This operation requires permissions for the ``lex:CreateSlotTypeVersion`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/CreateSlotTypeVersion>`_


========
Synopsis
========

::

    create-slot-type-version
  --name <value>
  [--checksum <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the slot type that you want to create a new version for. The name is case sensitive. 

  

``--checksum`` (string)


  Checksum for the ``$LATEST`` version of the slot type that you want to publish. If you specify a checksum and the ``$LATEST`` version of the slot type has a different checksum, Amazon Lex returns a ``PreconditionFailedException`` exception and doesn't publish the new version. If you don't specify a checksum, Amazon Lex publishes the ``$LATEST`` version.

  

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

  

  The date that the slot type was updated. When you create a resource, the creation date and last update date are the same.

  

  

createdDate -> (timestamp)

  

  The date that the slot type was created.

  

  

version -> (string)

  

  The version assigned to the new slot type version. 

  

  

checksum -> (string)

  

  Checksum of the ``$LATEST`` version of the slot type.

  

  

