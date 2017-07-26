[ :ref:`aws <cli:aws>` . :ref:`waf-regional <cli:aws waf-regional>` ]

.. _cli:aws waf-regional get-change-token-status:


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
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-regional-2016-11-28/GetChangeTokenStatus>`_


========
Synopsis
========

::

    get-change-token-status
  --change-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--change-token`` (string)


  The change token for which you want to get the status. This change token was previously returned in the ``get-change-token`` response.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ChangeTokenStatus -> (string)

  

  The status of the change token.

  

  

