[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds reset-db-parameter-group:


************************
reset-db-parameter-group
************************



===========
Description
===========



Modifies the parameters of a DB parameter group to the engine/system default value. To reset specific parameters, provide a list of the following: ``ParameterName`` and ``ApplyMethod`` . To reset the entire DB parameter group, specify the ``DBParameterGroup`` name and ``ResetAllParameters`` parameters. When resetting the entire group, dynamic parameters are updated immediately and static parameters are set to ``pending-reboot`` to take effect on the next DB instance restart or ``reboot-db-instance`` request. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/ResetDBParameterGroup>`_


========
Synopsis
========

::

    reset-db-parameter-group
  --db-parameter-group-name <value>
  [--reset-all-parameters | --no-reset-all-parameters]
  [--parameters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--db-parameter-group-name`` (string)


  The name of the DB parameter group.

   

  Constraints:

   

   
  * Must be 1 to 255 alphanumeric characters 
   
  * First character must be a letter 
   
  * Cannot end with a hyphen or contain two consecutive hyphens 
   

  

``--reset-all-parameters`` | ``--no-reset-all-parameters`` (boolean)


  Specifies whether (``true`` ) or not (``false`` ) to reset all parameters in the DB parameter group to default values. 

   

  Default: ``true``  

  

``--parameters`` (list)


  To reset the entire DB parameter group, specify the ``DBParameterGroup`` name and ``ResetAllParameters`` parameters. To reset specific parameters, provide a list of the following: ``ParameterName`` and ``ApplyMethod`` . A maximum of 20 parameters can be modified in a single request.

   

   **MySQL**  

   

  Valid Values (for Apply method): ``immediate`` | ``pending-reboot``  

   

  You can use the immediate value with dynamic parameters only. You can use the ``pending-reboot`` value for both dynamic and static parameters, and changes are applied when DB instance reboots.

   

   **MariaDB**  

   

  Valid Values (for Apply method): ``immediate`` | ``pending-reboot``  

   

  You can use the immediate value with dynamic parameters only. You can use the ``pending-reboot`` value for both dynamic and static parameters, and changes are applied when DB instance reboots.

   

   **Oracle**  

   

  Valid Values (for Apply method): ``pending-reboot``  

  



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

DBParameterGroupName -> (string)

  

  Provides the name of the DB parameter group.

  

  

