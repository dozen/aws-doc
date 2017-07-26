[ :ref:`aws <cli:aws>` . :ref:`datapipeline <cli:aws datapipeline>` ]

.. _cli:aws datapipeline describe-objects:


****************
describe-objects
****************



===========
Description
===========



Gets the object definitions for a set of objects associated with the pipeline. Object definitions are composed of a set of fields that define the properties of the object.



``describe-objects`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``pipelineObjects``


========
Synopsis
========

::

    describe-objects
  --pipeline-id <value>
  --object-ids <value>
  [--evaluate-expressions | --no-evaluate-expressions]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--pipeline-id`` (string)


  The ID of the pipeline that contains the object definitions.

  

``--object-ids`` (list)


  The IDs of the pipeline objects that contain the definitions to be described. You can pass as many as 25 identifiers in a single call to ``describe-objects`` .

  



Syntax::

  "string" "string" ...



``--evaluate-expressions`` | ``--no-evaluate-expressions`` (boolean)


  Indicates whether any expressions in the object should be evaluated when the object descriptions are returned.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON marker provided. The JSON marker follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

pipelineObjects -> (list)

  

  An array of object definitions.

  

  (structure)

    

    Contains information about a pipeline object. This can be a logical, physical, or physical attempt pipeline object. The complete set of components of a pipeline defines the pipeline.

    

    id -> (string)

      

      The ID of the object.

      

      

    name -> (string)

      

      The name of the object.

      

      

    fields -> (list)

      

      Key-value pairs that define the properties of the object.

      

      (structure)

        

        A key-value pair that describes a property of a pipeline object. The value is specified as either a marker value (``StringValue`` ) or a reference to another object (``RefValue`` ) but not as both.

        

        key -> (string)

          

          The field identifier.

          

          

        stringValue -> (string)

          

          The field value, expressed as a String.

          

          

        refValue -> (string)

          

          The field value, expressed as the identifier of another object.

          

          

        

      

    

  

marker -> (string)

  

  The starting point for the next page of results. To view the next page of results, call ``describe-objects`` again with this marker value. If the value is null, there are no more results.

  

  

hasMoreResults -> (boolean)

  

  Indicates whether there are more results to return.

  

  

