[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache modify-cache-parameter-group:


****************************
modify-cache-parameter-group
****************************



===========
Description
===========



The *modify-cache-parameter-group* action modifies the parameters of a cache parameter group. You can modify up to 20 parameters in a single request by submitting a list parameter name and value pairs.



========
Synopsis
========

::

    modify-cache-parameter-group
  --cache-parameter-group-name <value>
  --parameter-name-values <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cache-parameter-group-name`` (string)


  The name of the cache parameter group to modify.

  

``--parameter-name-values`` (list)


  An array of parameter names and values for the parameter update. You must supply at least one parameter name and value; subsequent arguments are optional. A maximum of 20 parameters may be modified per request.

  



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

  

  

