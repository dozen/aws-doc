[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds modify-db-parameter-group:


*************************
modify-db-parameter-group
*************************



===========
Description
===========



Modifies the parameters of a DB parameter group. To modify more than one parameter, submit a list of the following: ``ParameterName`` , ``ParameterValue`` , and ``ApplyMethod`` . A maximum of 20 parameters can be modified in a single request. 

 

.. note::

   

  Changes to dynamic parameters are applied immediately. Changes to static parameters require a reboot without failover to the DB instance associated with the parameter group before the change can take effect. 

   

 

.. warning::

   

  After you modify a DB parameter group, you should wait at least 5 minutes before creating your first DB instance that uses that DB parameter group as the default parameter group. This allows Amazon RDS to fully complete the modify action before the parameter group is used as the default for a new DB instance. This is especially important for parameters that are critical when creating the default database for a DB instance, such as the character set for the default database defined by the ``character_set_database`` parameter. You can use the *Parameter Groups* option of the `Amazon RDS console`_ or the *describe-db-parameters* command to verify that your DB parameter group has been created or modified.

   



========
Synopsis
========

::

    modify-db-parameter-group
  --db-parameter-group-name <value>
  --parameters <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-parameter-group-name`` (string)


  The name of the DB parameter group. 

   

  Constraints:

   

   
  * Must be the name of an existing DB parameter group
   
  * Must be 1 to 255 alphanumeric characters
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   

  

``--parameters`` (list)


  An array of parameter names, values, and the apply method for the parameter update. At least one parameter name, value, and apply method must be supplied; subsequent arguments are optional. A maximum of 20 parameters can be modified in a single request. 

   

  Valid Values (for the application method): ``immediate | pending-reboot`` 

   

  .. note::

    You can use the immediate value with dynamic parameters only. You can use the pending-reboot value for both dynamic and static parameters, and changes are applied when you reboot the DB instance without failover. 

  



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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

DBParameterGroupName -> (string)

  

  Provides the name of the DB parameter group. 

  

  



.. _Amazon RDS console: https://console.aws.amazon.com/rds/
