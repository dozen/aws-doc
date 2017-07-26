[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift reset-cluster-parameter-group:


*****************************
reset-cluster-parameter-group
*****************************



===========
Description
===========



Sets one or more parameters of the specified parameter group to their default values and sets the source values of the parameters to "engine-default". To reset the entire parameter group specify the *ResetAllParameters* parameter. For parameter changes to take effect you must reboot any associated clusters. 



========
Synopsis
========

::

    reset-cluster-parameter-group
  --parameter-group-name <value>
  [--reset-all-parameters | --no-reset-all-parameters]
  [--parameters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--parameter-group-name`` (string)


  The name of the cluster parameter group to be reset. 

  

``--reset-all-parameters`` | ``--no-reset-all-parameters`` (boolean)


  If ``true`` , all parameters in the specified parameter group will be reset to their default values. 

   

  Default: ``true`` 

  

``--parameters`` (list)


  An array of names of parameters to be reset. If *ResetAllParameters* option is not used, then at least one parameter name must be supplied. 

   

  Constraints: A maximum of 20 parameters can be reset in a single request.

  



Shorthand Syntax::

    ParameterName=string,ParameterValue=string,Description=string,Source=string,DataType=string,AllowedValues=string,ApplyType=string,IsModifiable=boolean,MinimumEngineVersion=string ...




JSON Syntax::

  [
    {
      "ParameterName": "string",
      "ParameterValue": "string",
      "Description": "string",
      "Source": "string",
      "DataType": "string",
      "AllowedValues": "string",
      "ApplyType": "static"|"dynamic",
      "IsModifiable": true|false,
      "MinimumEngineVersion": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

Reset Parameters in a Parameter Group
-------------------------------------

This example shows how to reset all of the parameters in a parameter group.

Command::

   aws redshift reset-cluster-parameter-group --parameter-group-name myclusterparametergroup --reset-all-parameters



======
Output
======

ParameterGroupName -> (string)

  

  The name of the cluster parameter group. 

  

  

ParameterGroupStatus -> (string)

  

  The status of the parameter group. For example, if you made a change to a parameter group name-value pair, then the change could be pending a reboot of an associated cluster. 

  

  

