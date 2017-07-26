[ :ref:`aws <cli:aws>` . :ref:`waf-regional <cli:aws waf-regional>` ]

.. _cli:aws waf-regional delete-xss-match-set:


********************
delete-xss-match-set
********************



===========
Description
===========



Permanently deletes an  XssMatchSet . You can't delete an ``XssMatchSet`` if it's still used in any ``Rules`` or if it still contains any  XssMatchTuple objects.

 

If you just want to remove an ``XssMatchSet`` from a ``Rule`` , use  update-rule .

 

To permanently delete an ``XssMatchSet`` from AWS WAF, perform the following steps:

 

 
* Update the ``XssMatchSet`` to remove filters, if any. For more information, see  update-xss-match-set . 
 
* Use  get-change-token to get the change token that you provide in the ``change-token`` parameter of a ``delete-xss-match-set`` request. 
 
* Submit a ``delete-xss-match-set`` request. 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-regional-2016-11-28/DeleteXssMatchSet>`_


========
Synopsis
========

::

    delete-xss-match-set
  --xss-match-set-id <value>
  --change-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--xss-match-set-id`` (string)


  The ``XssMatchSetId`` of the  XssMatchSet that you want to delete. ``XssMatchSetId`` is returned by  create-xss-match-set and by  list-xss-match-sets .

  

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

  

  The ``change-token`` that you used to submit the ``delete-xss-match-set`` request. You can also use this value to query the status of the request. For more information, see  get-change-token-status .

  

  

