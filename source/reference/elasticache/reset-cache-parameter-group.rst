[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache reset-cache-parameter-group:


***************************
reset-cache-parameter-group
***************************



===========
Description
===========



The *reset-cache-parameter-group* action modifies the parameters of a cache parameter group to the engine or system default value. You can reset specific parameters by submitting a list of parameter names. To reset the entire cache parameter group, specify the *ResetAllParameters* and *CacheParameterGroupName* parameters.



========
Synopsis
========

::

    reset-cache-parameter-group
  --cache-parameter-group-name <value>
  [--reset-all-parameters | --no-reset-all-parameters]
  --parameter-name-values <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cache-parameter-group-name`` (string)


  The name of the cache parameter group to reset.

  

``--reset-all-parameters`` | ``--no-reset-all-parameters`` (boolean)


  If *true* , all parameters in the cache parameter group will be reset to default values. If *false* , no such action occurs.

   

  Valid values: ``true`` | ``false`` 

  

``--parameter-name-values`` (list)


  An array of parameter names to be reset. If you are not resetting the entire cache parameter group, you must specify at least one parameter name.

  



Shorthand Syntax::

    ParameterName=string,ParameterValue=string ...




JSON Syntax::

  [
    {
      "ParameterName": "string",
      "ParameterValue": "string"
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

CacheParameterGroupName -> (string)

  

  The name of the cache parameter group.

  

  

