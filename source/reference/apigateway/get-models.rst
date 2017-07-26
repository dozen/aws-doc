[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-models:


**********
get-models
**********



===========
Description
===========



Describes existing  Models defined for a  RestApi resource.



``get-models`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``items``


========
Synopsis
========

::

    get-models
  --rest-api-id <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--rest-api-id`` (string)


  The  RestApi identifier.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

position -> (string)

  

  

items -> (list)

  

  Gets the current  Model resource in the collection.

  

  (structure)

    

    Represents the structure of a request or response payload for a method.

    

    id -> (string)

      

      The identifier for the model resource.

      

      

    name -> (string)

      

      The name of the model.

      

      

    description -> (string)

      

      The description of the model.

      

      

    schema -> (string)

      

      The schema for the model. For ``application/json`` models, this should be `JSON-schema draft v4`_ model.

      

      

    contentType -> (string)

      

      The content-type for the model.

      

      

    

  



.. _JSON-schema draft v4: http://json-schema.org/documentation.html
