[ :ref:`aws <cli:aws>` . :ref:`discovery <cli:aws discovery>` ]

.. _cli:aws discovery disassociate-configuration-items-from-application:


*************************************************
disassociate-configuration-items-from-application
*************************************************



===========
Description
===========



Disassociates one or more configuration items from an application.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/discovery-2015-11-01/DisassociateConfigurationItemsFromApplication>`_


========
Synopsis
========

::

    disassociate-configuration-items-from-application
  --application-configuration-id <value>
  --configuration-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-configuration-id`` (string)


  Configuration ID of an application from which each item is disassociated.

  

``--configuration-ids`` (list)


  Configuration ID of each item to be disassociated from an application.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

