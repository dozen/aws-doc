[ :ref:`aws <cli:aws>` . :ref:`opsworkscm <cli:aws opsworkscm>` . :ref:`wait <cli:aws opsworkscm wait>` ]

.. _cli:aws opsworkscm wait node-associated:


***************
node-associated
***************



===========
Description
===========

Wait until node is associated or disassociated. It will poll every 15 seconds until a successful state has been reached. This will exit with a return code of 255 after 15 failed checks.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworkscm-2016-11-01/DescribeNodeAssociationStatus>`_


========
Synopsis
========

::

    node-associated
  --node-association-status-token <value>
  --server-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--node-association-status-token`` (string)


``--server-name`` (string)


  The name of the server from which to disassociate the node. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None