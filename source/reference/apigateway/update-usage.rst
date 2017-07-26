[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway update-usage:


************
update-usage
************



===========
Description
===========



Grants a temporary extension to the remaining quota of a usage plan associated with a specified API key.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/UpdateUsage>`_


========
Synopsis
========

::

    update-usage
  --usage-plan-id <value>
  --key-id <value>
  [--patch-operations <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--usage-plan-id`` (string)


  The Id of the usage plan associated with the usage data.

  

``--key-id`` (string)


  The identifier of the API key associated with the usage plan in which a temporary extension is granted to the remaining quota.

  

``--patch-operations`` (list)


  A list of update operations to be applied to the specified resource and in the order specified in this list.

  



Shorthand Syntax::

    op=string,path=string,value=string,from=string ...




JSON Syntax::

  [
    {
      "op": "add"|"remove"|"replace"|"move"|"copy"|"test",
      "path": "string",
      "value": "string",
      "from": "string"
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

**To temporarily modify the quota on an API key for the current period defined in the Usage Plan**

Command::

  aws apigateway update-usage --usage-plan-id a1b2c3 --key-id 1NbjQzMReAkeEQPNAW8r3dXsU2rDD7fc7f2Sipnu --patch-operations op="replace",path="/remaining",value="50"


======
Output
======

usagePlanId -> (string)

  

  The plan Id associated with this usage data.

  

  

startDate -> (string)

  

  The starting date of the usage data.

  

  

endDate -> (string)

  

  The ending date of the usage data.

  

  

position -> (string)

  

  

items -> (map)

  

  The usage data, as daily logs of used and remaining quotas, over the specified time interval indexed over the API keys in a usage plan. For example, ``{..., "values" : { "{api_key}" : [ [0, 100], [10, 90], [100, 10]]}`` , where ``{api_key}`` stands for an API key value and the daily log entry is of the format ``[used quota, remaining quota]`` .

  

  key -> (string)

    

    

  value -> (list)

    

    (list)

      

      (long)

        

        

      

    

  

