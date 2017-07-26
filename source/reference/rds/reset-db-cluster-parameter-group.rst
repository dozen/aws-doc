[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds reset-db-cluster-parameter-group:


********************************
reset-db-cluster-parameter-group
********************************



===========
Description
===========



Modifies the parameters of a DB cluster parameter group to the default value. To reset specific parameters submit a list of the following: ``ParameterName`` and ``ApplyMethod`` . To reset the entire DB cluster parameter group, specify the ``DBClusterParameterGroupName`` and ``ResetAllParameters`` parameters. 

 

When resetting the entire group, dynamic parameters are updated immediately and static parameters are set to ``pending-reboot`` to take effect on the next DB instance restart or  reboot-db-instance request. You must call  reboot-db-instance for every DB instance in your DB cluster that you want the updated static parameter to apply to.

 

For more information on Amazon Aurora, see `Aurora on Amazon RDS`_ in the *Amazon RDS User Guide.* 



========
Synopsis
========

::

    reset-db-cluster-parameter-group
  --db-cluster-parameter-group-name <value>
  [--reset-all-parameters | --no-reset-all-parameters]
  [--parameters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-cluster-parameter-group-name`` (string)


  The name of the DB cluster parameter group to reset.

  

``--reset-all-parameters`` | ``--no-reset-all-parameters`` (boolean)


  A value that is set to ``true`` to reset all parameters in the DB cluster parameter group to their default values, and ``false`` otherwise. You cannot use this parameter if there is a list of parameter names specified for the ``Parameters`` parameter.

  

``--parameters`` (list)


  A list of parameter names in the DB cluster parameter group to reset to the default values. You cannot use this parameter if the ``ResetAllParameters`` parameter is set to ``true`` .

  



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

DBClusterParameterGroupName -> (string)

  

  The name of the DB cluster parameter group. 

   

  Constraints: 

   

   
  * Must be 1 to 255 alphanumeric characters
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   

   

  .. note::

    This value is stored as a lowercase string.

  

  



.. _Aurora on Amazon RDS: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Aurora.html
