[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift create-hsm-client-certificate:


*****************************
create-hsm-client-certificate
*****************************



===========
Description
===========



Creates an HSM client certificate that an Amazon Redshift cluster will use to connect to the client's HSM in order to store and retrieve the keys used to encrypt the cluster databases.

 

The command returns a public key, which you must store in the HSM. In addition to creating the HSM certificate, you must create an Amazon Redshift HSM configuration that provides a cluster the information needed to store and use encryption keys in the HSM. For more information, go to `Hardware Security Modules`_ in the Amazon Redshift Cluster Management Guide.



========
Synopsis
========

::

    create-hsm-client-certificate
  --hsm-client-certificate-identifier <value>
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--hsm-client-certificate-identifier`` (string)


  The identifier to be assigned to the new HSM client certificate that the cluster will use to connect to the HSM to use the database encryption keys.

  

``--tags`` (list)


  A list of tag instances.

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

HsmClientCertificate -> (structure)

  

  Returns information about an HSM client certificate. The certificate is stored in a secure Hardware Storage Module (HSM), and used by the Amazon Redshift cluster to encrypt data files.

  

  HsmClientCertificateIdentifier -> (string)

    

    The identifier of the HSM client certificate.

    

    

  HsmClientCertificatePublicKey -> (string)

    

    The public key that the Amazon Redshift cluster will use to connect to the HSM. You must register the public key in the HSM.

    

    

  Tags -> (list)

    

    The list of tags for the HSM client certificate.

    

    (structure)

      

      A tag consisting of a name/value pair for a resource.

      

      Key -> (string)

        

        The key, or name, for the resource tag.

        

        

      Value -> (string)

        

        The value for the resource tag.

        

        

      

    

  



.. _Hardware Security Modules: http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-HSM.html
