[ :ref:`aws <cli:aws>` . :ref:`discovery <cli:aws discovery>` ]

.. _cli:aws discovery export-configurations:


*********************
export-configurations
*********************



===========
Description
===========



Deprecated. Use ``start-export-task`` instead.

 

Exports all discovered configuration data to an Amazon S3 bucket or an application that enables you to view and evaluate the data. Data includes tags and tag associations, processes, connections, servers, and system performance. This API returns an export ID that you can query using the *describe-export-configurations* API. The system imposes a limit of two configuration exports in six hours.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/discovery-2015-11-01/ExportConfigurations>`_


========
Synopsis
========

::

    export-configurations
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

exportId -> (string)

  

  A unique identifier that you can use to query the export status.

  

  

