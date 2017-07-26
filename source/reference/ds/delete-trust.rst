[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds delete-trust:


************
delete-trust
************



===========
Description
===========

Deletes an existing trust relationship between your Microsoft AD in the AWS cloud and an external domain.

========
Synopsis
========

::

    delete-trust
  --trust-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--trust-id`` (string)
The Trust ID of the trust relationship to be deleted.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

TrustId -> (string)

  The Trust ID of the trust relationship that was deleted.

  

