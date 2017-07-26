[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory detach-object:


*************
detach-object
*************



===========
Description
===========



Detaches a given object from the parent object. The object that is to be detached from the parent is specified by the link name.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/DetachObject>`_


========
Synopsis
========

::

    detach-object
  --directory-arn <value>
  --parent-reference <value>
  --link-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-arn`` (string)


  The Amazon Resource Name (ARN) that is associated with the  Directory where objects reside. For more information, see  arns .

  

``--parent-reference`` (structure)


  The parent reference from which the object with the specified link name is detached.

  



Shorthand Syntax::

    Selector=string




JSON Syntax::

  {
    "Selector": "string"
  }



``--link-name`` (string)


  The link name associated with the object that needs to be detached.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DetachedObjectIdentifier -> (string)

  

  The ``ObjectIdentifier`` that was detached from the object.

  

  

