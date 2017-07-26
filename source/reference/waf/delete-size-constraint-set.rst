[ :ref:`aws <cli:aws>` . :ref:`waf <cli:aws waf>` ]

.. _cli:aws waf delete-size-constraint-set:


**************************
delete-size-constraint-set
**************************



===========
Description
===========



Permanently deletes a  SizeConstraintSet . You can't delete a ``SizeConstraintSet`` if it's still used in any ``Rules`` or if it still includes any  SizeConstraint objects (any filters).

 

If you just want to remove a ``SizeConstraintSet`` from a ``Rule`` , use  update-rule .

 

To permanently delete a ``SizeConstraintSet`` , perform the following steps:

 

 
* Update the ``SizeConstraintSet`` to remove filters, if any. For more information, see  update-size-constraint-set .
 
* Use  get-change-token to get the change token that you provide in the ``change-token`` parameter of a ``delete-size-constraint-set`` request.
 
* Submit a ``delete-size-constraint-set`` request.
 



========
Synopsis
========

::

    delete-size-constraint-set
  --size-constraint-set-id <value>
  --change-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--size-constraint-set-id`` (string)


  The ``SizeConstraintSetId`` of the  SizeConstraintSet that you want to delete. ``SizeConstraintSetId`` is returned by  create-size-constraint-set and by  list-size-constraint-sets .

  

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

  

  The ``change-token`` that you used to submit the ``delete-size-constraint-set`` request. You can also use this value to query the status of the request. For more information, see  get-change-token-status .

  

  

