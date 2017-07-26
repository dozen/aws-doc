[ :ref:`aws <cli:aws>` . :ref:`importexport <cli:aws importexport>` ]

.. _cli:aws importexport update-job:


**********
update-job
**********



===========
Description
===========

You use this operation to change the parameters specified in the original manifest file by supplying a new manifest file. The manifest file attached to this request replaces the original manifest file. You can only use the operation after a create-job request but before the data transfer starts and you can only use it on jobs you own.

========
Synopsis
========

::

    update-job
  --job-id <value>
  --manifest <value>
  --job-type <value>
  --validate-only | --no-validate-only
  [--api-version <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--job-id`` (string)
A unique identifier which refers to a particular job.

``--manifest`` (string)
The UTF-8 encoded text of the manifest file.

``--job-type`` (string)
Specifies whether the job to initiate is an import or export job.

  Possible values:

  
  *   ``Import``

  
  *   ``Export``

  

  

``--validate-only`` | ``--no-validate-only`` (boolean)
Validate the manifest and parameter values in the request but do not actually create a job.

``--api-version`` (string)
Specifies the version of the client tool.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command updates the specified job::

  aws importexport update-job --job-id EX1ID --job-type import --manifest file://manifest.txt --no-validate-only

The output for the update-jobs command looks like the following::

  True    **** Device will be erased before being returned. ****

With this command, you can either modify the original manifest you submitted, or you can start over and create a new manifest file. In either case, the original manifest is discarded.


======
Output
======

Success -> (boolean)

  Specifies whether (true) or not (false) AWS Import/Export updated your job.

  

WarningMessage -> (string)

  An optional message notifying you of non-fatal issues with the job, such as use of an incompatible Amazon S3 bucket name.

  

ArtifactList -> (list)

  A collection of artifacts.

  (structure)

    A discrete item that contains the description and URL of an artifact (such as a PDF).

    Description -> (string)

      The associated description for this object.

      

    URL -> (string)

      The URL for a given Artifact.

      

    

  

