[ :ref:`aws <cli:aws>` . :ref:`waf-regional <cli:aws waf-regional>` ]

.. _cli:aws waf-regional get-change-token:


****************
get-change-token
****************



===========
Description
===========



When you want to create, update, or delete AWS WAF objects, get a change token and include the change token in the create, update, or delete request. Change tokens ensure that your application doesn't submit conflicting requests to AWS WAF.

 

Each create, update, or delete request must use a unique change token. If your application submits a ``get-change-token`` request and then submits a second ``get-change-token`` request before submitting a create, update, or delete request, the second ``get-change-token`` request returns the same value as the first ``get-change-token`` request.

 

When you use a change token in a create, update, or delete request, the status of the change token changes to ``PENDING`` , which indicates that AWS WAF is propagating the change to all AWS WAF servers. Use ``get-change-token-status`` to determine the status of your change token.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/waf-regional-2016-11-28/GetChangeToken>`_


========
Synopsis
========

::

    get-change-token
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ChangeToken -> (string)

  

  The ``ChangeToken`` that you used in the request. Use this value in a ``get-change-token-status`` request to get the current status of the request. 

  

  

