[ :ref:`aws <cli:aws>` . :ref:`waf <cli:aws waf>` ]

.. _cli:aws waf delete-byte-match-set:


*********************
delete-byte-match-set
*********************



===========
Description
===========



Permanently deletes a  ByteMatchSet . You can't delete a ``ByteMatchSet`` if it's still used in any ``Rules`` or if it still includes any  ByteMatchTuple objects (any filters).

 

If you just want to remove a ``ByteMatchSet`` from a ``Rule`` , use  update-rule .

 

To permanently delete a ``ByteMatchSet`` , perform the following steps:

 

 
* Update the ``ByteMatchSet`` to remove filters, if any. For more information, see  update-byte-match-set .
 
* Use  get-change-token to get the change token that you provide in the ``change-token`` parameter of a ``delete-byte-match-set`` request.
 
* Submit a ``delete-byte-match-set`` request.
 



========
Synopsis
========

::

    delete-byte-match-set
  --byte-match-set-id <value>
  --change-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--byte-match-set-id`` (string)


  The ``ByteMatchSetId`` of the  ByteMatchSet that you want to delete. ``ByteMatchSetId`` is returned by  create-byte-match-set and by  list-byte-match-sets .

  

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

  

  The ``change-token`` that you used to submit the ``delete-byte-match-set`` request. You can also use this value to query the status of the request. For more information, see  get-change-token-status .

  

  

