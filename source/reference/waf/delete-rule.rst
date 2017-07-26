[ :ref:`aws <cli:aws>` . :ref:`waf <cli:aws waf>` ]

.. _cli:aws waf delete-rule:


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
 



========
Synopsis
========

::

    delete-rule
  --rule-id <value>
  --change-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--rule-id`` (string)


  The ``RuleId`` of the  Rule that you want to delete. ``RuleId`` is returned by  create-rule and by  list-rules .

  

``--change-token`` (string)


  The value returned by the most recent call to  get-change-token .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ChangeToken -> (string)

  

  The ``change-token`` that you used to submit the ``delete-rule`` request. You can also use this value to query the status of the request. For more information, see  get-change-token-status .

  

  

