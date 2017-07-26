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

 

For more information on Amazon Aurora, see `Aurora on Amazon RDS <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Aurora.html>`_ in the *Amazon RDS User Guide.*  



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/ResetDBClusterParameterGroup>`_


========
Synopsis
========

::

    reset-db-cluster-parameter-group
  --db-cluster-parameter-group-name <value>
  [--reset-all-parameters | --no-reset-all-parameters]
  [--parameters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

     

  

  

