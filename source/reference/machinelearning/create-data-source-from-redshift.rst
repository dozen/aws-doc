[ :ref:`aws <cli:aws>` . :ref:`machinelearning <cli:aws machinelearning>` ]

.. _cli:aws machinelearning create-data-source-from-redshift:


********************************
create-data-source-from-redshift
********************************



===========
Description
===========



Creates a ``DataSource`` from `Amazon Redshift`_ . A ``DataSource`` references data that can be used to perform either  create-ml-model ,  create-evaluation or  create-batch-prediction operations.

 

``create-data-source-from-redshift`` is an asynchronous operation. In response to ``create-data-source-from-redshift`` , Amazon Machine Learning (Amazon ML) immediately returns and sets the ``DataSource`` status to ``PENDING`` . After the ``DataSource`` is created and ready for use, Amazon ML sets the ``Status`` parameter to ``COMPLETED`` . ``DataSource`` in ``COMPLETED`` or ``PENDING`` status can only be used to perform  create-ml-model ,  create-evaluation , or  create-batch-prediction operations. 

 

If Amazon ML cannot accept the input source, it sets the ``Status`` parameter to ``FAILED`` and includes an error message in the ``Message`` attribute of the  get-data-source operation response. 

 

The observations should exist in the database hosted on an Amazon Redshift cluster and should be specified by a ``SelectSqlQuery`` . Amazon ML executes `Unload`_ command in Amazon Redshift to transfer the result set of ``SelectSqlQuery`` to ``S3StagingLocation.``  

 

After the ``DataSource`` is created, it's ready for use in evaluations and batch predictions. If you plan to use the ``DataSource`` to train an ``MLModel`` , the ``DataSource`` requires another item -- a recipe. A recipe describes the observation variables that participate in training an ``MLModel`` . A recipe describes how each input variable will be used in training. Will the variable be included or excluded from training? Will the variable be manipulated, for example, combined with another variable or split apart into word combinations? The recipe provides answers to these questions. For more information, see the Amazon Machine Learning Developer Guide.



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
  [--generate-cli-skeleton]




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

     
    * ``DatabaseName`` - Name of the Amazon Redshift database. 
     
    * ``ClusterIdentifier`` - Unique ID for the Amazon Redshift cluster.
     

  

  
   
  * DatabaseCredentials - AWS Identity abd Access Management (IAM) credentials that are used to connect to the Amazon Redshift database.
   
  * SelectSqlQuery - Query that is used to retrieve the observation data for the ``Datasource`` .
   
  * S3StagingLocation - Amazon Simple Storage Service (Amazon S3) location for staging Amazon Redshift data. The data retrieved from Amazon Relational Database Service (Amazon RDS) using ``SelectSqlQuery`` is stored in this location.
   
  * DataSchemaUri - Amazon S3 location of the ``DataSchema`` .
   
  * DataSchema - A JSON string representing the schema. This is not required if ``DataSchemaUri`` is specified. 
   
  * DataRearrangement - A JSON string representing the splitting requirement of a ``Datasource`` .   Sample - ``"{\"splitting\":{\"percentBegin\":10,\"percentEnd\":60}}"``   
   

  



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


  The compute statistics for a ``DataSource`` . The statistics are generated from the observation data referenced by a ``DataSource`` . Amazon ML uses the statistics internally during ``MLModel`` training. This parameter must be set to ``true`` if the ```` DataSource```` needs to be used for ``MLModel`` training

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

DataSourceId -> (string)

  

  A user-supplied ID that uniquely identifies the datasource. This value should be identical to the value of the ``DataSourceID`` in the request. 

  

  



.. _Amazon Redshift: http://aws.amazon.com/redshift/
.. _Unload: http://docs.aws.amazon.com/redshift/latest/dg/t_Unloading_tables.html
