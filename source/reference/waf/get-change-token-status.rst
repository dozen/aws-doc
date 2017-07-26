[ :ref:`aws <cli:aws>` . :ref:`waf <cli:aws waf>` ]

.. _cli:aws waf get-change-token-status:


***********************
get-change-token-status
***********************



===========
Description
===========



Returns the status of a ``change-token`` that you got by calling  get-change-token . ``ChangeTokenStatus`` is one of the following values:

 

 
* ``PROVISIONED`` : You requested the change token by calling ``get-change-token`` , but you haven't used it yet in a call to create, update, or delete an AWS WAF object.
 
* ``PENDING`` : AWS WAF is propagating the create, update, or delete request to all AWS WAF servers.
 
* ``IN_SYNC`` : Propagation is complete.
 



========
Synopsis
========

::

    get-change-token-status
  --change-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--change-token`` (string)


  The change token for which you want to get the status. This change token was previously returned in the ``get-change-token`` response.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ChangeTokenStatus -> (string)

  

  The status of the change token.

  

  

