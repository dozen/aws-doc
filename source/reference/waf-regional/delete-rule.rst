[ :ref:`aws <cli:aws>` . :ref:`waf-regional <cli:aws waf-regional>` ]

.. _cli:aws waf-regional delete-rule:


***********
delete-rule
***********



===========
Description
===========



Permanently deletes a  Rule . You can't delete a ``Rule`` if it's still used in any ``WebACL`` objects or if it still includes any predicates, such as ``ByteMatchSet`` objects.

 

If you just want to remove a ``Rule`` from a ``WebACL`` , use  update-web-acl .

 

To permanently delete a ``Rule`` from AWS WAF, perform the following steps:

 

 
* Update the ``Rule`` to remove predicates, if any. For more information, see  update-rule . 
 
* Use  get-change-token to get the change token that you provide in the ``change-token`` parameter of a ``delete-rule`` request. 
 
* Submit a ``delete-rule`` request. 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-regional-2016-11-28/DeleteRule>`_


========
Synopsis
========

::

    delete-rule
  --rule-id <value>
  --change-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rule-id`` (string)


  The ``RuleId`` of the  Rule that you want to delete. ``RuleId`` is returned by  create-rule and by  list-rules .

  

``--change-token`` (string)


  The value returned by the most recent call to  get-change-token .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ChangeToken -> (string)

  

  The ``change-token`` that you used to submit the ``delete-rule`` request. You can also use this value to query the status of the request. For more information, see  get-change-token-status .

  

  

