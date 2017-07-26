[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory create-index:


************
create-index
************



===========
Description
===========



Creates an index object. See `Indexing <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/cd_indexing.html>`_ for more information.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/CreateIndex>`_


========
Synopsis
========

::

    create-index
  --directory-arn <value>
  --ordered-indexed-attribute-list <value>
  --is-unique | --no-is-unique
  [--parent-reference <value>]
  [--link-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-arn`` (string)


  The ARN of the directory where the index should be created.

  

``--ordered-indexed-attribute-list`` (list)


  Specifies the attributes that should be indexed on. Currently only a single attribute is supported.

  



Shorthand Syntax::

    SchemaArn=string,FacetName=string,Name=string ...




JSON Syntax::

  [
    {
      "SchemaArn": "string",
      "FacetName": "string",
      "Name": "string"
    }
    ...
  ]



``--is-unique`` | ``--no-is-unique`` (boolean)


  Indicates whether the attribute that is being indexed has unique values or not.

  

``--parent-reference`` (structure)


  A reference to the parent object that contains the index object.

  



Shorthand Syntax::

    Selector=string




JSON Syntax::

  {
    "Selector": "string"
  }



``--link-name`` (string)


  The name of the link between the parent object and the index object.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ObjectIdentifier -> (string)

  

  The ``ObjectIdentifier`` of the index created by this operation.

  

  

