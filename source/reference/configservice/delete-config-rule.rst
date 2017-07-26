[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice delete-config-rule:


******************
delete-config-rule
******************



===========
Description
===========



Deletes the specified AWS Config rule and all of its evaluation results.

 

AWS Config sets the state of a rule to ``DELETING`` until the deletion is complete. You cannot update a rule while it is in this state. If you make a ``put-config-rule`` request for the rule, you will receive a ``ResourceInUseException`` .

 

You can check the state of a rule by using the ``describe-config-rules`` request.



========
Synopsis
========

::

    delete-config-rule
  --config-rule-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--config-rule-name`` (string)


  The name of the AWS Config rule that you want to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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