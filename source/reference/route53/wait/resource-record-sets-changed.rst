[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` . :ref:`wait <cli:aws route53 wait>` ]

.. _cli:aws route53 wait resource-record-sets-changed:


****************************
resource-record-sets-changed
****************************



===========
Description
===========

Wait until JMESPath query ChangeInfo.Status returns INSYNC when polling with ``get-change``. It will poll every 30 seconds until a successful state has been reached. This will exit with a return code of 255 after 60 failed checks.

========
Synopsis
========

::

    resource-record-sets-changed
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--id`` (string)


  The ID of the change batch request. The value that you specify here is the value that ``change-resource-record-sets`` returned in the Id element when you submitted the request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None