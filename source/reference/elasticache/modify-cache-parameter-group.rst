[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache modify-cache-parameter-group:


****************************
modify-cache-parameter-group
****************************



===========
Description
===========



Modifies the parameters of a cache parameter group. You can modify up to 20 parameters in a single request by submitting a list parameter name and value pairs.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticache-2015-02-02/ModifyCacheParameterGroup>`_


========
Synopsis
========

::

    modify-cache-parameter-group
  --cache-parameter-group-name <value>
  --parameter-name-values <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To modify cache parameter groups**

This example modifies parameters for the specified cache parameter group.

Command::

  aws elasticache modify-cache-parameter-group \
  --cache-parameter-group-name my-redis-28 --parameter-name-values \
  ParameterName=close-on-slave-write,ParameterValue=no \
  ParameterName=timeout,ParameterValue=60

Output::

  {
      "CacheParameterGroupName": "my-redis-28"
  }



======
Output
======

CacheParameterGroupName -> (string)

  

  The name of the cache parameter group.

  

  

