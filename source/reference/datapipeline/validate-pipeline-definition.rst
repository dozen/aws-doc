[ :ref:`aws <cli:aws>` . :ref:`datapipeline <cli:aws datapipeline>` ]

.. _cli:aws datapipeline validate-pipeline-definition:


****************************
validate-pipeline-definition
****************************



===========
Description
===========



Validates the specified pipeline definition to ensure that it is well formed and can be run without error.



========
Synopsis
========

::

    validate-pipeline-definition
  --pipeline-id <value>
  --pipeline-objects <value>
  [--parameter-objects <value>]
  [--parameter-values <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--pipeline-id`` (string)


  The ID of the pipeline.

  

``--pipeline-objects`` (list)


  The objects that define the pipeline changes to validate against the pipeline.

  



Shorthand Syntax::

    id=string,name=string,fields=[{key=string,stringValue=string,refValue=string},{key=string,stringValue=string,refValue=string}] ...




JSON Syntax::

  [
    {
      "id": "string",
      "name": "string",
      "fields": [
        {
          "key": "string",
          "stringValue": "string",
          "refValue": "string"
        }
        ...
      ]
    }
    ...
  ]



``--parameter-objects`` (list)


  The parameter objects used with the pipeline.

  



Shorthand Syntax::

    id=string,attributes=[{key=string,stringValue=string},{key=string,stringValue=string}] ...




JSON Syntax::

  [
    {
      "id": "string",
      "attributes": [
        {
          "key": "string",
          "stringValue": "string"
        }
        ...
      ]
    }
    ...
  ]



``--parameter-values`` (list)


  The parameter values used with the pipeline.

  



Shorthand Syntax::

    id=string,stringValue=string ...




JSON Syntax::

  [
    {
      "id": "string",
      "stringValue": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

validationErrors -> (list)

  

  Any validation errors that were found.

  

  (structure)

    

    Defines a validation error. Validation errors prevent pipeline activation. The set of validation errors that can be returned are defined by AWS Data Pipeline.

    

    id -> (string)

      

      The identifier of the object that contains the validation error.

      

      

    errors -> (list)

      

      A description of the validation error.

      

      (string)

        

        

      

    

  

validationWarnings -> (list)

  

  Any validation warnings that were found.

  

  (structure)

    

    Defines a validation warning. Validation warnings do not prevent pipeline activation. The set of validation warnings that can be returned are defined by AWS Data Pipeline.

    

    id -> (string)

      

      The identifier of the object that contains the validation warning.

      

      

    warnings -> (list)

      

      A description of the validation warning.

      

      (string)

        

        

      

    

  

errored -> (boolean)

  

  Indicates whether there were validation errors.

  

  

