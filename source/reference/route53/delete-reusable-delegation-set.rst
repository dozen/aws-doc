[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 delete-reusable-delegation-set:


******************************
delete-reusable-delegation-set
******************************



===========
Description
===========



This action deletes a reusable delegation set. To delete a reusable delegation set, send a ``DELETE`` request to the ``/*Route 53 API version* /delegationset/*delegation set ID*`` resource.

 

.. warning::

  You can delete a reusable delegation set only if there are no associated hosted zones. If your reusable delegation set contains associated hosted zones, you must delete them before you can delete your reusable delegation set. If you try to delete a reusable delegation set that contains associated hosted zones, Amazon Route 53 will deny your request with a ``DelegationSetInUse`` error.



========
Synopsis
========

::

    delete-reusable-delegation-set
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--id`` (string)


  The ID of the reusable delegation set you want to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

