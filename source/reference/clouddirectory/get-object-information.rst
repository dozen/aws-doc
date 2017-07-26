[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory get-object-information:


**********************
get-object-information
**********************



===========
Description
===========



Retrieves metadata about an object.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/GetObjectInformation>`_


========
Synopsis
========

::

    get-object-information
  --directory-arn <value>
  --object-reference <value>
  [--consistency-level <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-arn`` (string)


  The ARN of the directory being retrieved.

  

``--object-reference`` (structure)


  A reference to the object.

  



Shorthand Syntax::

    Selector=string




JSON Syntax::

  {
    "Selector": "string"
  }



``--consistency-level`` (string)


  The consistency level at which to retrieve the object information.

  

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

SchemaFacets -> (list)

  

  The facets attached to the specified object.

  

  (structure)

    

    A facet.

    

    SchemaArn -> (string)

      

      The ARN of the schema that contains the facet.

      

      

    FacetName -> (string)

      

      The name of the facet.

      

      

    

  

ObjectIdentifier -> (string)

  

  The ``ObjectIdentifier`` of the specified object.

  

  

