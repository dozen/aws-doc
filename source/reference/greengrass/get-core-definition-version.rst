[ :ref:`aws <cli:aws>` . :ref:`greengrass <cli:aws greengrass>` ]

.. _cli:aws greengrass get-core-definition-version:


***************************
get-core-definition-version
***************************



===========
Description
===========

Retrieves information about a core definition version.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/greengrass-2017-06-07/GetCoreDefinitionVersion>`_


========
Synopsis
========

::

    get-core-definition-version
  --core-definition-id <value>
  --core-definition-version-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--core-definition-id`` (string)
core definition Id

``--core-definition-version-id`` (string)
core definition version Id

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Arn -> (string)

  Arn of the core definition version.

  

CreationTimestamp -> (string)

  Timestamp of when the core definition version was created.

  

Definition -> (structure)

  Information on definition

  Cores -> (list)

    Cores in the definition version.

    (structure)

      Information on the core

      CertificateArn -> (string)

        Certificate arn of the core.

        

      Id -> (string)

        Element Id for this entry in the list.

        

      SyncShadow -> (boolean)

        If true, the local shadow value automatically syncs with the cloud's shadow state.

        

      ThingArn -> (string)

        Thing arn of the core.

        

      

    

  

Id -> (string)

  Id of the core definition the version belongs to.

  

Version -> (string)

  Version of the core definition version.

  

