[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning create-data-source-from-s3:


**************************
create-data-source-from-s3
**************************



===========
Description
===========



Creates a ``DataSource`` object. A ``DataSource`` references data that can be used to perform  create-ml-model ,  create-evaluation , or  create-batch-prediction operations.

 

``create-data-source-from-s3`` is an asynchronous operation. In response to ``create-data-source-from-s3`` , Amazon Machine Learning (Amazon ML) immediately returns and sets the ``DataSource`` status to ``PENDING`` . After the ``DataSource`` is created and ready for use, Amazon ML sets the ``Status`` parameter to ``COMPLETED`` . ``DataSource`` in ``COMPLETED`` or ``PENDING`` status can only be used to perform  create-ml-model ,  create-evaluation or  create-batch-prediction operations. 

 

If Amazon ML cannot accept the input source, it sets the ``Status`` parameter to ``FAILED`` and includes an error message in the ``Message`` attribute of the  get-data-source operation response. 

 

The observation data used in a ``DataSource`` should be ready to use; that is, it should have a consistent structure, and missing data values should be kept to a minimum. The observation data must reside in one or more CSV files in an Amazon Simple Storage Service (Amazon S3) bucket, along with a schema that describes the data items by name and type. The same schema must be used for all of the data files referenced by the ``DataSource`` . 

 

After the ``DataSource`` has been created, it's ready to use in evaluations and batch predictions. If you plan to use the ``DataSource`` to train an ``MLModel`` , the ``DataSource`` requires another item: a recipe. A recipe describes the observation variables that participate in training an ``MLModel`` . A recipe describes how each input variable will be used in training. Will the variable be included or excluded from training? Will the variable be manipulated, for example, combined with another variable, or split apart into word combinations? The recipe provides answers to these questions. For more information, see the `Amazon Machine Learning Developer Guide`_ .



========
Synopsis
========

::

    create-data-source-from-s3
  --data-source-id <value>
  [--data-source-name <value>]
  --data-spec <value>
  [--compute-statistics | --no-compute-statistics]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--data-source-id`` (string)


  A user-supplied identifier that uniquely identifies the ``DataSource`` . 

  

``--data-source-name`` (string)


  A user-supplied name or description of the ``DataSource`` . 

  

``--data-spec`` (structure)


  The data specification of a ``DataSource`` :

   

   
  * DataLocationS3 - Amazon Simple Storage Service (Amazon S3) location of the observation data.
   
  * DataSchemaLocationS3 - Amazon S3 location of the ``DataSchema`` .
   
  * DataSchema - A JSON string representing the schema. This is not required if ``DataSchemaUri`` is specified. 
   
  * DataRearrangement - A JSON string representing the splitting requirement of a ``Datasource`` .   Sample - ``"{\"splitting\":{\"percentBegin\":10,\"percentEnd\":60}}"``   
   

  



Shorthand Syntax::

    DataLocationS3=string,DataRearrangement=string,DataSchema=string,DataSchemaLocationS3=string




JSON Syntax::

  {
    "DataLocationS3": "string",
    "DataRearrangement": "string",
    "DataSchema": "string",
    "DataSchemaLocationS3": "string"
  }



``--compute-statistics`` | ``--no-compute-statistics`` (boolean)


  The compute statistics for a ``DataSource`` . The statistics are generated from the observation data referenced by a ``DataSource`` . Amazon ML uses the statistics internally during an ``MLModel`` training. This parameter must be set to ``true`` if the ```` DataSource```` needs to be used for ``MLModel`` training

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

DataSourceId -> (string)

  

  A user-supplied ID that uniquely identifies the datasource. This value should be identical to the value of the ``DataSourceID`` in the request. 

  

  



.. _Amazon Machine Learning Developer Guide: http://docs.aws.amazon.com/machine-learning/latest/dg
