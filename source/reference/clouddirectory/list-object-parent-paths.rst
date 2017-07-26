[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory list-object-parent-paths:


************************
list-object-parent-paths
************************



===========
Description
===========



Retrieves all available parent paths for any object type such as node, leaf node, policy node, and index node objects. For more information about objects, see `Directory Structure <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/cd_key_concepts.html#dirstructure>`_ .

 

Use this API to evaluate all parents for an object. The call returns all objects from the root of the directory up to the requested object. The API returns the number of paths based on user-defined ``MaxResults`` , in case there are multiple paths to the parent. The order of the paths and nodes returned is consistent among multiple API calls unless the objects are deleted or moved. Paths not leading to the directory root are ignored from the target object.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/ListObjectParentPaths>`_


========
Synopsis
========

::

    list-object-parent-paths
  --directory-arn <value>
  --object-reference <value>
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-arn`` (string)


  The ARN of the directory to which the parent path applies.

  

``--object-reference`` (structure)


  The reference that identifies the object whose parent paths are listed.

  



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

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

PathToObjectIdentifiersList -> (list)

  

  Returns the path to the ``ObjectIdentifiers`` that are associated with the directory.

  

  (structure)

    

    Returns the path to the ``ObjectIdentifiers`` that is associated with the directory.

    

    Path -> (string)

      

      The path that is used to identify the object starting from directory root.

      

      

    ObjectIdentifiers -> (list)

      

      Lists ``ObjectIdentifiers`` starting from directory root to the object in the request.

      

      (string)

        

        

      

    

  

NextToken -> (string)

  

  The pagination token.

  

  

