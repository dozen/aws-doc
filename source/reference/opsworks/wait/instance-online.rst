[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` . :ref:`wait <cli:aws opsworks wait>` ]

.. _cli:aws opsworks wait instance-online:


***************
instance-online
***************



===========
Description
===========

Wait until OpsWorks instance is online. It will poll every 15 seconds until a successful state has been reached. This will exit with a return code of 255 after 40 failed checks.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/DescribeInstances>`_


========
Synopsis
========

::

    instance-online
  [--stack-id <value>]
  [--layer-id <value>]
  [--instance-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-id`` (string)


  A stack ID. If you use this parameter, ``describe-instances`` returns descriptions of the instances associated with the specified stack.

  

``--layer-id`` (string)


  A layer ID. If you use this parameter, ``describe-instances`` returns descriptions of the instances associated with the specified layer.

  

``--instance-ids`` (list)


  An array of instance IDs to be described. If you use this parameter, ``describe-instances`` returns a description of the specified instances. Otherwise, it returns a description of every instance.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None