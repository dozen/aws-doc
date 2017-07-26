[ :ref:`aws <cli:aws>` . :ref:`sms <cli:aws sms>` ]

.. _cli:aws sms import-server-catalog:


*********************
import-server-catalog
*********************



===========
Description
===========

The import-server-catalog API is used to gather the complete list of on-premises servers on your premises. This API call requires connectors to be installed and monitoring all servers you would like imported. This API call returns immediately, but may take some time to retrieve all of the servers.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sms-2016-10-24/ImportServerCatalog>`_


========
Synopsis
========

::

    import-server-catalog
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

