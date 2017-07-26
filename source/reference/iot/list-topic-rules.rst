[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot list-topic-rules:


****************
list-topic-rules
****************



===========
Description
===========



Lists the rules for the specific topic.



========
Synopsis
========

::

    list-topic-rules
  [--topic <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--rule-disabled | --no-rule-disabled]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--topic`` (string)


  The topic.

  

``--max-results`` (integer)


  The maximum number of results to return.

  

``--next-token`` (string)


  A token used to retrieve the next value.

  

``--rule-disabled`` | ``--no-rule-disabled`` (boolean)


  Specifies whether the rule is disabled.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

rules -> (list)

  

  The rules.

  

  (structure)

    

    Describes a rule.

    

    ruleArn -> (string)

      

      The rule ARN.

      

      

    ruleName -> (string)

      

      The name of the rule.

      

      

    topicPattern -> (string)

      

      The pattern for the topic names that apply.

      

      

    createdAt -> (timestamp)

      

      The date and time the rule was created.

      

      

    ruleDisabled -> (boolean)

      

      Specifies whether the rule is disabled.

      

      

    

  

nextToken -> (string)

  

  A token used to retrieve the next value.

  

  

