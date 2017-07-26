[ :ref:`aws <cli:aws>` . :ref:`sdb <cli:aws sdb>` ]

.. _cli:aws sdb delete-domain:


*************
delete-domain
*************



===========
Description
===========



The ``delete-domain`` operation deletes a domain. Any items (and their attributes) in the domain are deleted as well. The ``delete-domain`` operation might take 10 or more seconds to complete. 



.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.sdb true`` 



========
Synopsis
========

::

    delete-domain
  --domain-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-name`` (string)
The name of the domain to delete.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None