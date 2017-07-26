[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway delete-usage-plan:


*****************
delete-usage-plan
*****************



===========
Description
===========



Deletes a usage plan of a given plan Id.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/DeleteUsagePlan>`_


========
Synopsis
========

::

    delete-usage-plan
  --usage-plan-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--usage-plan-id`` (string)


  The Id of the to-be-deleted usage plan.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a Usage Plan**

Command::

  aws apigateway delete-usage-plan --usage-plan-id a1b2c3


======
Output
======

None