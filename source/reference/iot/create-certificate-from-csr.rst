[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot create-certificate-from-csr:


***************************
create-certificate-from-csr
***************************



===========
Description
===========



Creates an X.509 certificate using the specified certificate signing request.

 

**Note** Reusing the same certificate signing request (CSR) results in a distinct certificate.

 

You can create multiple certificates in a batch by creating a directory and copying multiple .csr files into that directory and specifying that directory on the command line. The following commands show how to create a batch of certificates given a batch of CSRs. 

 

Assuming a set of CSRs are located inside of the directory my-csr-directory:

 

On Linux and OSX, the command is:

 

$ ls my-csr-directory/ | xargs -I {} aws iot create-certificate-from-csr --certificate-signing-request file://my-csr-directory/{}

 

This command lists all of the CSRs in my-csr-directory and pipes each CSR filename to the aws iot create-certificate-from-csr AWS CLI command to create a certificate for the corresponding CSR. 

 

The aws iot create-certificate-from-csr part of the command can also be run in parallel to speed up the certificate creation process: 

 

$ ls my-csr-directory/ | xargs -P 10 -I {} aws iot create-certificate-from-csr --certificate-signing-request file://my-csr-directory/{} 

 

On Windows PowerShell, the command to create certificates for all CSRs in my-csr-directory is: 

 

 ls -Name my-csr-directory | %{aws iot create-certificate-from-csr --certificate-signing-request file://my-csr-directory/$_} 

 

On Windows Command Prompt, the command to create certificates for all CSRs in my-csr-directory is: 

 

 forfiles /p my-csr-directory /c "cmd /c aws iot create-certificate-from-csr --certificate-signing-request file://@path"



========
Synopsis
========

::

    create-certificate-from-csr
  --certificate-signing-request <value>
  [--set-as-active | --no-set-as-active]
  [--certificate-pem-outfile <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  

