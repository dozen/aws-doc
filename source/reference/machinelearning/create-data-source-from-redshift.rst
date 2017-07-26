[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning create-data-source-from-redshift:


********************************
create-data-source-from-redshift
********************************



===========
Description
===========



Creates a ``DataSource`` from a database hosted on an Amazon Redshift cluster. A ``DataSource`` references data that can be used to perform either ``create-ml-model`` , ``create-evaluation`` , or ``create-batch-prediction`` operations.

 

``create-data-source-from-redshift`` is an asynchronous operation. In response to ``create-data-source-from-redshift`` , Amazon Machine Learning (Amazon ML) immediately returns and sets the ``DataSource`` status to ``PENDING`` . After the ``DataSource`` is created and ready for use, Amazon ML sets the ``Status`` parameter to ``COMPLETED`` . ``DataSource`` in ``COMPLETED`` or ``PENDING`` states can be used to perform only ``create-ml-model`` , ``create-evaluation`` , or ``create-batch-prediction`` operations. 

 

If Amazon ML can't accept the input source, it sets the ``Status`` parameter to ``FAILED`` and includes an error message in the ``Message`` attribute of the ``get-data-source`` operation response. 

 

The observations should be contained in the database hosted on an Amazon Redshift cluster and should be specified by a ``SelectSqlQuery`` query. Amazon ML executes an ``Unload`` command in Amazon Redshift to transfer the result set of the ``SelectSqlQuery`` query to ``S3StagingLocation`` .

 

After the ``DataSource`` has been created, it's ready for use in evaluations and batch predictions. If you plan to use the ``DataSource`` to train an ``MLModel`` , the ``DataSource`` also requires a recipe. A recipe describes how each input variable will be used in training an ``MLModel`` . Will the variable be included or excluded from training? Will the variable be manipulated; for example, will it be combined with another variable or will it be split apart into word combinations? The recipe provides answers to these questions.

 

You can't change an existing datasource, but you can copy and modify the settings from an existing Amazon Redshift datasource to create a new datasource. To do so, call ``get-data-source`` for an existing datasource and copy the values to a ``CreateDataSource`` call. Change the settings that you want to change and make sure that all required fields have the appropriate values.

 

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/machinelearning-2014-12-12/CreateDataSourceFromRedshift>`_


========
Synopsis
========

::

    create-data-source-from-redshift
  --data-source-id <value>
  [--data-source-name <value>]
  --data-spec <value>
  --role-arn <value>
  [--compute-statistics | --no-compute-statistics]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--data-source-id`` (string)


  A user-supplied ID that uniquely identifies the ``DataSource`` .

  

``--data-source-name`` (string)


  A user-supplied name or description of the ``DataSource`` . 

  

``--data-spec`` (structure)


  The data specification of an Amazon Redshift ``DataSource`` :

   

   
  * DatabaseInformation - 

     
    * ``DatabaseName`` - The name of the Amazon Redshift database. 
     
    * ``ClusterIdentifier`` - The unique ID for the Amazon Redshift cluster.
     

  

  
   
  * DatabaseCredentials - The AWS Identity and Access Management (IAM) credentials that are used to connect to the Amazon Redshift database.
   
  * SelectSqlQuery - The query that is used to retrieve the observation data for the ``Datasource`` .
   
  * S3StagingLocation - The Amazon Simple Storage Service (Amazon S3) location for staging Amazon Redshift data. The data retrieved from Amazon Redshift using the ``SelectSqlQuery`` query is stored in this location.
   
  * DataSchemaUri - The Amazon S3 location of the ``DataSchema`` .
   
  * DataSchema - A JSON string representing the schema. This is not required if ``DataSchemaUri`` is specified. 
   
  * DataRearrangement - A JSON string that represents the splitting and rearrangement requirements for the ``DataSource`` . Sample - ``"{\"splitting\":{\"percentBegin\":10,\"percentEnd\":60}}"``   
   

  



Shorthand Syntax::

    DatabaseInformation={DatabaseName=string,ClusterIdentifier=string},SelectSqlQuery=string,DatabaseCredentials={Username=string,Password=string},S3StagingLocation=string,DataRearrangement=string,DataSchema=string,DataSchemaUri=string




JSON Syntax::

  {
    "DatabaseInformation": {
      "DatabaseName": "string",
      "ClusterIdentifier": "string"
    },
    "SelectSqlQuery": "string",
    "DatabaseCredentials": {
      "Username": "string",
      "Password": "string"
    },
    "S3StagingLocation": "string",
    "DataRearrangement": "string",
    "DataSchema": "string",
    "DataSchemaUri": "string"
  }



``--role-arn`` (string)


  A fully specified role Amazon Resource Name (ARN). Amazon ML assumes the role on behalf of the user to create the following: 

   

   

   
  * A security group to allow Amazon ML to execute the ``SelectSqlQuery`` query on an Amazon Redshift cluster
   
  * An Amazon S3 bucket policy to grant Amazon ML read/write permissions on the ``S3StagingLocation`` 
   

   

  

``--compute-statistics`` | ``--no-compute-statistics`` (boolean)


  The compute statistics for a ``DataSource`` . The statistics are generated from the observation data referenced by a ``DataSource`` . Amazon ML uses the statistics internally during ``MLModel`` training. This parameter must be set to ``true`` if the ``DataSource`` needs to be used for ``MLModel`` training.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DataSourceId -> (string)

  

  A user-supplied ID that uniquely identifies the datasource. This value should be identical to the value of the ``DataSourceID`` in the request. 

  

  

