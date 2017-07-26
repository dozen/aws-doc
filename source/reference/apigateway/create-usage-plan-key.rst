[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway create-usage-plan-key:


*********************
create-usage-plan-key
*********************



===========
Description
===========



Creates a usage plan key for adding an existing API key to a usage plan.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/CreateUsagePlanKey>`_


========
Synopsis
========

::

    create-usage-plan-key
  --usage-plan-id <value>
  --key-id <value>
  --key-type <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--usage-plan-id`` (string)


  The Id of the  UsagePlan resource representing the usage plan containing the to-be-created  UsagePlanKey resource representing a plan customer.

  

``--key-id`` (string)


  The identifier of a  UsagePlanKey resource for a plan customer.

  

``--key-type`` (string)


  The type of a  UsagePlanKey resource for a plan customer.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**Associate an existing API key with a Usage Plan**

Command::

  aws apigateway create-usage-plan-key --usage-plan-id a1b2c3 --key-type "API_KEY" --key-id 4vq3yryqm5


======
Output
======

id -> (string)

  

  The Id of a usage plan key.

  

  

type -> (string)

  

  The type of a usage plan key. Currently, the valid key type is ``API_KEY`` .

  

  

value -> (string)

  

  The value of a usage plan key.

  

  

name -> (string)

  

  The name of a usage plan key.

  

  

