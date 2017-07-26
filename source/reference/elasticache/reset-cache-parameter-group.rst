[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache reset-cache-parameter-group:


***************************
reset-cache-parameter-group
***************************



===========
Description
===========



Modifies the parameters of a cache parameter group to the engine or system default value. You can reset specific parameters by submitting a list of parameter names. To reset the entire cache parameter group, specify the ``ResetAllParameters`` and ``CacheParameterGroupName`` parameters.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticache-2015-02-02/ResetCacheParameterGroup>`_


========
Synopsis
========

::

    reset-cache-parameter-group
  --cache-parameter-group-name <value>
  [--reset-all-parameters | --no-reset-all-parameters]
  [--parameter-name-values <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cache-parameter-group-name`` (string)


  The name of the cache parameter group to reset.

  

``--reset-all-parameters`` | ``--no-reset-all-parameters`` (boolean)


  If ``true`` , all parameters in the cache parameter group are reset to their default values. If ``false`` , only the parameters listed by ``ParameterNameValues`` are reset to their default values.

   

  Valid values: ``true`` | ``false``  

  

``--parameter-name-values`` (list)


  An array of parameter names to reset to their default values. If ``ResetAllParameters`` is ``true`` , do not use ``ParameterNameValues`` . If ``ResetAllParameters`` is ``false`` , you must specify the name of at least one parameter to reset.

  



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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

CacheParameterGroupName -> (string)

  

  The name of the cache parameter group.

  

  

