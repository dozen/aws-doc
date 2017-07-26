[ :ref:`aws <cli:aws>` . :ref:`waf-regional <cli:aws waf-regional>` ]

.. _cli:aws waf-regional delete-ip-set:


*************
delete-ip-set
*************



===========
Description
===========



Permanently deletes an  IPSet . You can't delete an ``IPSet`` if it's still used in any ``Rules`` or if it still includes any IP addresses.

 

If you just want to remove an ``IPSet`` from a ``Rule`` , use  update-rule .

 

To permanently delete an ``IPSet`` from AWS WAF, perform the following steps:

 

 
* Update the ``IPSet`` to remove IP address ranges, if any. For more information, see  update-ip-set . 
 
* Use  get-change-token to get the change token that you provide in the ``change-token`` parameter of a ``delete-ip-set`` request. 
 
* Submit a ``delete-ip-set`` request. 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-regional-2016-11-28/DeleteIPSet>`_


========
Synopsis
========

::

    delete-ip-set
  --ip-set-id <value>
  --change-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--ip-set-id`` (string)


  The ``IPSetId`` of the  IPSet that you want to delete. ``IPSetId`` is returned by  create-ip-set and by  list-ip-sets .

  

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

  

  The ``change-token`` that you used to submit the ``delete-ip-set`` request. You can also use this value to query the status of the request. For more information, see  get-change-token-status .

  

  

