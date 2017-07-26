[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds modify-db-cluster-parameter-group:


*********************************
modify-db-cluster-parameter-group
*********************************



===========
Description
===========



Modifies the parameters of a DB cluster parameter group. To modify more than one parameter, submit a list of the following: ``ParameterName`` , ``ParameterValue`` , and ``ApplyMethod`` . A maximum of 20 parameters can be modified in a single request. 

 

For more information on Amazon Aurora, see `Aurora on Amazon RDS <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Aurora.html>`_ in the *Amazon RDS User Guide.*  

 

.. note::

   

  Changes to dynamic parameters are applied immediately. Changes to static parameters require a reboot without failover to the DB cluster associated with the parameter group before the change can take effect.

   

 

.. warning::

   

  After you create a DB cluster parameter group, you should wait at least 5 minutes before creating your first DB cluster that uses that DB cluster parameter group as the default parameter group. This allows Amazon RDS to fully complete the create action before the parameter group is used as the default for a new DB cluster. This is especially important for parameters that are critical when creating the default database for a DB cluster, such as the character set for the default database defined by the ``character_set_database`` parameter. You can use the *Parameter Groups* option of the `Amazon RDS console <https://console.aws.amazon.com/rds/>`_ or the  describe-db-cluster-parameters command to verify that your DB cluster parameter group has been created or modified.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/ModifyDBClusterParameterGroup>`_


========
Synopsis
========

::

    modify-db-cluster-parameter-group
  --db-cluster-parameter-group-name <value>
  --parameters <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--db-cluster-parameter-group-name`` (string)


  The name of the DB cluster parameter group to modify.

  

``--parameters`` (list)


  A list of parameters in the DB cluster parameter group to modify.

  



Shorthand Syntax::

    ParameterName=string,ParameterValue=string,Description=string,Source=string,ApplyType=string,DataType=string,AllowedValues=string,IsModifiable=boolean,MinimumEngineVersion=string,ApplyMethod=string ...




JSON Syntax::

  [
    {
      "ParameterName": "string",
      "ParameterValue": "string",
      "Description": "string",
      "Source": "string",
      "ApplyType": "string",
      "DataType": "string",
      "AllowedValues": "string",
      "IsModifiable": true|false,
      "MinimumEngineVersion": "string",
      "ApplyMethod": "immediate"|"pending-reboot"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DBClusterParameterGroupName -> (string)

  

  The name of the DB cluster parameter group.

   

  Constraints:

   

   
  * Must be 1 to 255 alphanumeric characters 
   
  * First character must be a letter 
   
  * Cannot end with a hyphen or contain two consecutive hyphens 
   

   

  .. note::

     

    This value is stored as a lowercase string.

     

  

  

