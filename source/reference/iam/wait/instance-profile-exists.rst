[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` . :ref:`wait <cli:aws iam wait>` ]

.. _cli:aws iam wait instance-profile-exists:


***********************
instance-profile-exists
***********************



===========
Description
===========

Wait until 200 response is received when polling with ``get-instance-profile``. It will poll every 1 seconds until a successful state has been reached. This will exit with a return code of 255 after 40 failed checks.

========
Synopsis
========

::

    instance-profile-exists
  --instance-profile-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--instance-profile-name`` (string)


  The name of the instance profile to get information about.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None