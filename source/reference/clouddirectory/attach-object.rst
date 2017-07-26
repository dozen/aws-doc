[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory attach-object:


*************
attach-object
*************



===========
Description
===========



Attaches an existing object to another object. An object can be accessed in two ways:

 

 
* Using the path 
 
* Using ``ObjectIdentifier``   
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/AttachObject>`_


========
Synopsis
========

::

    attach-object
  --directory-arn <value>
  --parent-reference <value>
  --child-reference <value>
  --link-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-arn`` (string)


  Amazon Resource Name (ARN) that is associated with the  Directory where both objects reside. For more information, see  arns .

  

``--parent-reference`` (structure)


  The parent object reference.

  



Shorthand Syntax::

    Selector=string




JSON Syntax::

  {
    "Selector": "string"
  }



``--child-reference`` (structure)


  The child object reference to be attached to the object.

  



Shorthand Syntax::

    Selector=string




JSON Syntax::

  {
    "Selector": "string"
  }



``--link-name`` (string)


  The link name with which the child object is attached to the parent.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

AttachedObjectIdentifier -> (string)

  

  The attached ``ObjectIdentifier`` , which is the child ``ObjectIdentifier`` .

  

  

