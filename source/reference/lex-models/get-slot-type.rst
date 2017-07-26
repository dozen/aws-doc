[ :ref:`aws <cli:aws>` . :ref:`lex-models <cli:aws lex-models>` ]

.. _cli:aws lex-models get-slot-type:


*************
get-slot-type
*************



===========
Description
===========



Returns information about a specific version of a slot type. In addition to specifying the slot type name, you must specify the slot type version.

 

This operation requires permissions for the ``lex:GetSlotType`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lex-models-2017-04-19/GetSlotType>`_


========
Synopsis
========

::

    get-slot-type
  --name <value>
  --slot-type-version <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the slot type. The name is case sensitive. 

  

``--slot-type-version`` (string)


  The version of the slot type. 

  

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

  

  The version of the slot type.

  

  

checksum -> (string)

  

  Checksum of the ``$LATEST`` version of the slot type.

  

  

