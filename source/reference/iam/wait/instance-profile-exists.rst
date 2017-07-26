[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` . :ref:`wait <cli:aws iam wait>` ]

.. _cli:aws iam wait instance-profile-exists:


***********************
instance-profile-exists
***********************



===========
Description
===========

Wait until 200 response is received when polling with ``get-instance-profile``. It will poll every 1 seconds until a successful state has been reached. This will exit with a return code of 255 after 40 failed checks.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/GetInstanceProfile>`_


========
Synopsis
========

::

    instance-profile-exists
  --instance-profile-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-profile-name`` (string)


  The name of the instance profile to get information about.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None