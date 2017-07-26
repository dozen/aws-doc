[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` . :ref:`wait <cli:aws iam wait>` ]

.. _cli:aws iam wait user-exists:


***********
user-exists
***********



===========
Description
===========

Wait until 200 response is received when polling with ``get-user``. It will poll every 1 seconds until a successful state has been reached. This will exit with a return code of 255 after 20 failed checks.

========
Synopsis
========

::

    user-exists
  [--user-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--user-name`` (string)


  The name of the user to get information about.

   

  This parameter is optional. If it is not included, it defaults to the user making the request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None