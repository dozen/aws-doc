[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot create-certificate-from-csr:


***************************
create-certificate-from-csr
***************************



===========
Description
===========



Creates an X.509 certificate using the specified certificate signing request.

 

 **Note:** The CSR must include a public key that is either an RSA key with a length of at least 2048 bits or an ECC key from NIST P-256 or NIST P-384 curves. 

 

 **Note:** Reusing the same certificate signing request (CSR) results in a distinct certificate.

 

You can create multiple certificates in a batch by creating a directory, copying multiple .csr files into that directory, and then specifying that directory on the command line. The following commands show how to create a batch of certificates given a batch of CSRs.

 

Assuming a set of CSRs are located inside of the directory my-csr-directory:

 

On Linux and OS X, the command is:

 

$ ls my-csr-directory/ | xargs -I {} aws iot create-certificate-from-csr --certificate-signing-request file://my-csr-directory/{}

 

This command lists all of the CSRs in my-csr-directory and pipes each CSR file name to the aws iot create-certificate-from-csr AWS CLI command to create a certificate for the corresponding CSR.

 

The aws iot create-certificate-from-csr part of the command can also be run in parallel to speed up the certificate creation process:

 

$ ls my-csr-directory/ | xargs -P 10 -I {} aws iot create-certificate-from-csr --certificate-signing-request file://my-csr-directory/{}

 

On Windows PowerShell, the command to create certificates for all CSRs in my-csr-directory is:

 

ls -Name my-csr-directory | %{aws iot create-certificate-from-csr --certificate-signing-request file://my-csr-directory/$_}

 

On a Windows command prompt, the command to create certificates for all CSRs in my-csr-directory is:

 

forfiles /p my-csr-directory /c "cmd /c aws iot create-certificate-from-csr --certificate-signing-request file://@path"



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iot-2015-05-28/CreateCertificateFromCsr>`_


========
Synopsis
========

::

    create-certificate-from-csr
  --certificate-signing-request <value>
  [--set-as-active | --no-set-as-active]
  [--certificate-pem-outfile <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--certificate-signing-request`` (string)


  The certificate signing request (CSR).

  

``--set-as-active`` | ``--no-set-as-active`` (boolean)


  Specifies whether the certificate is active.

  

``--certificate-pem-outfile`` (string)
Saves the command output contents of certificatePem to the given filename

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

Create Batches of Certificates from Batches of CSRs
---------------------------------------------------
The following example shows how to create a batch of certificates given a
batch of CSRs. Assuming a set of CSRs are located inside of the
directory ``my-csr-directory``::

    $ ls my-csr-directory/
    csr.pem		csr2.pem


a certificate can be created for each CSR in that directory
using a single command. On Linux and OSX, this command is::

    $ ls my-csr-directory/ | xargs -I {} aws iot create-certificate-from-csr --certificate-signing-request file://my-csr-directory/{}


This command lists all of the CSRs in ``my-csr-directory`` and
pipes each CSR filename to the ``aws iot create-certificate-from-csr`` AWS CLI
command to create a certificate for the corresponding CSR.

The ``aws iot create-certificate-from-csr`` part of the command can also be
ran in parallel to speed up the certificate creation process::

    $ ls my-csr-directory/ | xargs -P 10 -I {} aws iot create-certificate-from-csr --certificate-signing-request file://my-csr-directory/{}


On Windows PowerShell, the command to create certificates for all CSRs
in ``my-csr-directory`` is::

    > ls -Name my-csr-directory | %{aws iot create-certificate-from-csr --certificate-signing-request file://my-csr-directory/$_}


On Windows Command Prompt, the command to create certificates for all CSRs
in ``my-csr-directory`` is::

    > forfiles /p my-csr-directory /c "cmd /c aws iot create-certificate-from-csr --certificate-signing-request file://@path"


======
Output
======

certificateArn -> (string)

  

  The Amazon Resource Name (ARN) of the certificate. You can use the ARN as a principal for policy operations.

  

  

certificateId -> (string)

  

  The ID of the certificate. Certificate management operations only take a certificateId.

  

  

certificatePem -> (string)

  

  The certificate data, in PEM format.

  

  

