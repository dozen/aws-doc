[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway update-usage-plan:


*****************
update-usage-plan
*****************



===========
Description
===========



Updates a usage plan of a given plan Id.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/UpdateUsagePlan>`_


========
Synopsis
========

::

    update-usage-plan
  --usage-plan-id <value>
  [--patch-operations <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--usage-plan-id`` (string)


  The Id of the to-be-updated usage plan.

  

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

**To change the period defined in a Usage Plan**

Command::

  aws apigateway update-usage-plan --usage-plan-id a1b2c3 --patch-operations op="replace",path="/quota/period",value="MONTH"

**To change the quota limit defined in a Usage Plan**

Command::

  aws apigateway update-usage-plan --usage-plan-id a1b2c3 --patch-operations op="replace",path="/quota/limit",value="500"

**To change the throttle rate limit defined in a Usage Plan**

Command::

  aws apigateway update-usage-plan --usage-plan-id a1b2c3 --patch-operations op="replace",path="/throttle/rateLimit",value="10"

**To change the throttle burst limit defined in a Usage Plan**

Command::

  aws apigateway update-usage-plan --usage-plan-id a1b2c3 --patch-operations op="replace",path="/throttle/burstLimit",value="20"


======
Output
======

id -> (string)

  

  The identifier of a  UsagePlan resource.

  

  

name -> (string)

  

  The name of a usage plan.

  

  

description -> (string)

  

  The description of a usage plan.

  

  

apiStages -> (list)

  

  The associated API stages of a usage plan.

  

  (structure)

    

    API stage name of the associated API stage in a usage plan.

    

    apiId -> (string)

      

      API Id of the associated API stage in a usage plan.

      

      

    stage -> (string)

      

      API stage name of the associated API stage in a usage plan.

      

      

    

  

throttle -> (structure)

  

  The request throttle limits of a usage plan.

  

  burstLimit -> (integer)

    

    The API request burst limit, the maximum rate limit over a time ranging from one to a few seconds, depending upon whether the underlying token bucket is at its full capacity.

    

    

  rateLimit -> (double)

    

    The API request steady-state rate limit.

    

    

  

quota -> (structure)

  

  The maximum number of permitted requests per a given unit time interval.

  

  limit -> (integer)

    

    The maximum number of requests that can be made in a given time period.

    

    

  offset -> (integer)

    

    The number of requests subtracted from the given limit in the initial time period.

    

    

  period -> (string)

    

    The time period in which the limit applies. Valid values are "DAY", "WEEK" or "MONTH".

    

    

  

productCode -> (string)

  

  The AWS Markeplace product identifier to associate with the usage plan as a SaaS product on AWS Marketplace.

  

  

