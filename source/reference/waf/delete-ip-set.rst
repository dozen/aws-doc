[ :ref:`aws <cli:aws>` . :ref:`waf <cli:aws waf>` ]

.. _cli:aws waf delete-ip-set:


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
 



========
Synopsis
========

::

    delete-ip-set
  --ip-set-id <value>
  --change-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--ip-set-id`` (string)


  The ``IPSetId`` of the  IPSet that you want to delete. ``IPSetId`` is returned by  create-ip-set and by  list-ip-sets .

  

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

  

  The ``change-token`` that you used to submit the ``delete-ip-set`` request. You can also use this value to query the status of the request. For more information, see  get-change-token-status .

  

  

