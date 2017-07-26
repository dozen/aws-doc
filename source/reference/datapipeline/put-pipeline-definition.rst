[ :ref:`aws <cli:aws>` . :ref:`datapipeline <cli:aws datapipeline>` ]

.. _cli:aws datapipeline put-pipeline-definition:


***********************
put-pipeline-definition
***********************



===========
Description
===========



Adds tasks, schedules, and preconditions to the specified pipeline. You can use ``put-pipeline-definition`` to populate a new pipeline.

 

 ``put-pipeline-definition`` also validates the configuration as it adds it to the pipeline. Changes to the pipeline are saved unless one of the following three validation errors exists in the pipeline. 

 

 
* An object is missing a name or identifier field.
 
* A string or reference field is empty.
 
* The number of objects in the pipeline exceeds the maximum allowed objects.
 
* The pipeline is in a FINISHED state.
 

 

Pipeline object definitions are passed to the ``put-pipeline-definition`` action and returned by the  get-pipeline-definition action. 



========
Synopsis
========

::

    put-pipeline-definition
  --pipeline-id <value>
  [--parameter-objects <value>]
  [--parameter-values <value>]
  --pipeline-definition <value>
  [--parameter-values-uri <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--pipeline-id`` (string)


  The ID of the pipeline.

  

``--parameter-objects`` (string)
The JSON parameter objects. If the parameter objects are in a file you can use the file://syntax to specify a filename. You can optionally provide these in pipeline definition as well. Parameter objects provided on command line would replace the one in definition. 

``--parameter-values`` (string)
The JSON parameter values. You can specify these as key-value pairs in the key=value format. Multiple parameters are separated by a space. For list type parameter values you can use the same key name and specify each value as a key value pair. e.g. arrayValue=value1 arrayValue=value2 

``--pipeline-definition`` (string)
The JSON pipeline definition. If the pipeline definition is in a file you can use the file://syntax to specify a filename. 

``--parameter-values-uri`` (string)
The JSON parameter values. If the parameter values are in a file you can use the file://syntax to specify a filename. You can optionally provide these in pipeline definition as well. Parameter values provided on command line would replace the one in definition. 

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To upload a pipeline definition**

This example uploads the specified pipeline definition to the specified pipeline::

   aws datapipeline put-pipeline-definition --pipeline-id df-00627471SOVYZEXAMPLE --pipeline-definition file://my-pipeline-definition.json
   
The following is example output::

  {
    "validationErrors": [],
    "errored": false,
    "validationWarnings": []
  }


======
Output
======

validationErrors -> (list)

  

  The validation errors that are associated with the objects defined in ``pipelineObjects`` .

  

  (structure)

    

    Defines a validation error. Validation errors prevent pipeline activation. The set of validation errors that can be returned are defined by AWS Data Pipeline.

    

    id -> (string)

      

      The identifier of the object that contains the validation error.

      

      

    errors -> (list)

      

      A description of the validation error.

      

      (string)

        

        

      

    

  

validationWarnings -> (list)

  

  The validation warnings that are associated with the objects defined in ``pipelineObjects`` .

  

  (structure)

    

    Defines a validation warning. Validation warnings do not prevent pipeline activation. The set of validation warnings that can be returned are defined by AWS Data Pipeline.

    

    id -> (string)

      

      The identifier of the object that contains the validation warning.

      

      

    warnings -> (list)

      

      A description of the validation warning.

      

      (string)

        

        

      

    

  

errored -> (boolean)

  

  Indicates whether there were validation errors, and the pipeline definition is stored but cannot be activated until you correct the pipeline and call ``put-pipeline-definition`` to commit the corrected pipeline.

  

  

