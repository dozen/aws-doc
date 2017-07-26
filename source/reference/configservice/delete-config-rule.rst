[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice delete-config-rule:


******************
delete-config-rule
******************



===========
Description
===========



Deletes the specified AWS Config rule and all of its evaluation results.

 

AWS Config sets the state of a rule to ``DELETING`` until the deletion is complete. You cannot update a rule while it is in this state. If you make a ``put-config-rule`` or ``delete-config-rule`` request for the rule, you will receive a ``ResourceInUseException`` .

 

You can check the state of a rule by using the ``describe-config-rules`` request.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/config-2014-11-12/DeleteConfigRule>`_


========
Synopsis
========

::

    delete-config-rule
  --config-rule-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--config-rule-name`` (string)


  The name of the AWS Config rule that you want to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete an AWS Config rule**

The following command deletes an AWS Config rule named ``MyConfigRule``::

    aws configservice delete-config-rule --config-rule-name MyConfigRule

======
Output
======

None