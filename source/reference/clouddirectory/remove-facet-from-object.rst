[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory remove-facet-from-object:


************************
remove-facet-from-object
************************



===========
Description
===========



Removes the specified facet from the specified object.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/RemoveFacetFromObject>`_


========
Synopsis
========

::

    remove-facet-from-object
  --directory-arn <value>
  --schema-facet <value>
  --object-reference <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-arn`` (string)


  The ARN of the directory in which the object resides.

  

``--schema-facet`` (structure)


  The facet to remove.

  



Shorthand Syntax::

    SchemaArn=string,FacetName=string




JSON Syntax::

  {
    "SchemaArn": "string",
    "FacetName": "string"
  }



``--object-reference`` (structure)


  A reference to the object to remove the facet from.

  



Shorthand Syntax::

    Selector=string




JSON Syntax::

  {
    "Selector": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

