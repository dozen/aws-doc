[ :ref:`aws <cli:aws>` . :ref:`importexport <cli:aws importexport>` ]

.. _cli:aws importexport create-job:


**********
create-job
**********



===========
Description
===========

This operation initiates the process of scheduling an upload or download of your data. You include in the request a manifest that describes the data transfer specifics. The response to the request includes a job ID, which you can use in other operations, a signature that you use to identify your storage device, and the address where you should ship your storage device.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/importexport-2010-06-01/CreateJob>`_


========
Synopsis
========

::

    create-job
  --job-type <value>
  --manifest <value>
  [--manifest-addendum <value>]
  --validate-only | --no-validate-only
  [--api-version <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--job-type`` (string)
Specifies whether the job to initiate is an import or export job.

  Possible values:

  
  *   ``Import``

  
  *   ``Export``

  

  

``--manifest`` (string)
The UTF-8 encoded text of the manifest file.

``--manifest-addendum`` (string)
For internal use only.

``--validate-only`` | ``--no-validate-only`` (boolean)
Validate the manifest and parameter values in the request but do not actually create a job.

``--api-version`` (string)
Specifies the version of the client tool.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command creates an import job from a manifest file::

  aws importexport create-job --job-type import --manifest file://manifest --no-validate-only

The file ``manifest`` is a YAML formatted text file in the current directory with the following content::

  manifestVersion: 2.0;
  returnAddress:
  name: Jane Roe
  company: Example Corp.
  street1: 123 Any Street
  city: Anytown
  stateOrProvince: WA
  postalCode: 91011-1111
  phoneNumber: 206-555-1111
  country: USA
  deviceId: 49382
  eraseDevice: yes
  notificationEmail: john.doe@example.com;jane.roe@example.com
  bucket: myBucket

For more information on the manifest file format, see `Creating Import Manifests`_ in the *AWS Import/Export Developer Guide*.

.. _`Creating Import Manifests`: http://docs.aws.amazon.com/AWSImportExport/latest/DG/ImportManifestFile.html
  
You can also pass the manifest as a string in quotes::

  aws importexport create-job --job-type import --manifest 'manifestVersion: 2.0;
   returnAddress:
   name: Jane Roe
   company: Example Corp.
   street1: 123 Any Street
   city: Anytown
   stateOrProvince: WA
   postalCode: 91011-1111
   phoneNumber: 206-555-1111
   country: USA
   deviceId: 49382
   eraseDevice: yes
   notificationEmail: john.doe@example.com;jane.roe@example.com
   bucket: myBucket'

For information on quoting string arguments and using files, see `Specifying Parameter Values`_ in the *AWS CLI User Guide*.

.. _`Specifying Parameter Values`: http://docs.aws.amazon.com/cli/latest/userguide/cli-using-param.html


======
Output
======

JobId -> (string)

  A unique identifier which refers to a particular job.

  

JobType -> (string)

  Specifies whether the job to initiate is an import or export job.

  

Signature -> (string)

  An encrypted code used to authenticate the request and response, for example, "DV+TpDfx1/TdSE9ktyK9k/bDTVI=". Only use this value is you want to create the signature file yourself. Generally you should use the SignatureFileContents value.

  

SignatureFileContents -> (string)

  The actual text of the SIGNATURE file to be written to disk.

  

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

      

    

  

