[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway create-usage-plan:


*****************
create-usage-plan
*****************



===========
Description
===========



Creates a usage plan with the throttle and quota limits, as well as the associated API stages, specified in the payload. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/CreateUsagePlan>`_


========
Synopsis
========

::

    create-usage-plan
  --name <value>
  [--description <value>]
  [--api-stages <value>]
  [--throttle <value>]
  [--quota <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the usage plan.

  

``--description`` (string)


  The description of the usage plan.

  

``--api-stages`` (list)


  The associated API stages of the usage plan.

  



Shorthand Syntax::

    apiId=string,stage=string ...




JSON Syntax::

  [
    {
      "apiId": "string",
      "stage": "string"
    }
    ...
  ]



``--throttle`` (structure)


  The throttling limits of the usage plan.

  



Shorthand Syntax::

    burstLimit=integer,rateLimit=double




JSON Syntax::

  {
    "burstLimit": integer,
    "rateLimit": double
  }



``--quota`` (structure)


  The quota of the usage plan.

  



Shorthand Syntax::

    limit=integer,offset=integer,period=string




JSON Syntax::

  {
    "limit": integer,
    "offset": integer,
    "period": "DAY"|"WEEK"|"MONTH"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a usage plan with throttle and quota limits that resets at the beginning of the month**

Command::

  aws apigateway create-usage-plan --name "New Usage Plan" --description "A new usage plan" --throttle burstLimit=10,rateLimit=5 --quota limit=500,offset=0,period=MONTH


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

  

  

