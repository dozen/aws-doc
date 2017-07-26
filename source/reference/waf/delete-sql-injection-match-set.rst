[ :ref:`aws <cli:aws>` . :ref:`waf <cli:aws waf>` ]

.. _cli:aws waf delete-sql-injection-match-set:


******************************
delete-sql-injection-match-set
******************************



===========
Description
===========



Permanently deletes a  SqlInjectionMatchSet . You can't delete a ``SqlInjectionMatchSet`` if it's still used in any ``Rules`` or if it still contains any  SqlInjectionMatchTuple objects.

 

If you just want to remove a ``SqlInjectionMatchSet`` from a ``Rule`` , use  update-rule .

 

To permanently delete a ``SqlInjectionMatchSet`` from AWS WAF, perform the following steps:

 

 
* Update the ``SqlInjectionMatchSet`` to remove filters, if any. For more information, see  update-sql-injection-match-set .
 
* Use  get-change-token to get the change token that you provide in the ``change-token`` parameter of a ``delete-sql-injection-match-set`` request.
 
* Submit a ``delete-sql-injection-match-set`` request.
 



========
Synopsis
========

::

    delete-sql-injection-match-set
  --sql-injection-match-set-id <value>
  --change-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--sql-injection-match-set-id`` (string)


  The ``SqlInjectionMatchSetId`` of the  SqlInjectionMatchSet that you want to delete. ``SqlInjectionMatchSetId`` is returned by  create-sql-injection-match-set and by  list-sql-injection-match-sets .

  

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

  

  The ``change-token`` that you used to submit the ``delete-sql-injection-match-set`` request. You can also use this value to query the status of the request. For more information, see  get-change-token-status .

  

  

