[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift create-hsm-configuration:


************************
create-hsm-configuration
************************



===========
Description
===========



Creates an HSM configuration that contains the information required by an Amazon Redshift cluster to store and use database encryption keys in a Hardware Security Module (HSM). After creating the HSM configuration, you can specify it as a parameter when creating a cluster. The cluster will then store its encryption keys in the HSM.

 

In addition to creating an HSM configuration, you must also create an HSM client certificate. For more information, go to `Hardware Security Modules`_ in the Amazon Redshift Cluster Management Guide.



========
Synopsis
========

::

    create-hsm-configuration
  --hsm-configuration-identifier <value>
  --description <value>
  --hsm-ip-address <value>
  --hsm-partition-name <value>
  --hsm-partition-password <value>
  --hsm-server-public-certificate <value>
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--hsm-configuration-identifier`` (string)


  The identifier to be assigned to the new Amazon Redshift HSM configuration.

  

``--description`` (string)


  A text description of the HSM configuration to be created.

  

``--hsm-ip-address`` (string)


  The IP address that the Amazon Redshift cluster must use to access the HSM.

  

``--hsm-partition-name`` (string)


  The name of the partition in the HSM where the Amazon Redshift clusters will store their database encryption keys.

  

``--hsm-partition-password`` (string)


  The password required to access the HSM partition.

  

``--hsm-server-public-certificate`` (string)


  The HSMs public certificate file. When using Cloud HSM, the file name is server.pem.

  

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

HsmConfiguration -> (structure)

  

  Returns information about an HSM configuration, which is an object that describes to Amazon Redshift clusters the information they require to connect to an HSM where they can store database encryption keys.

  

  HsmConfigurationIdentifier -> (string)

    

    The name of the Amazon Redshift HSM configuration.

    

    

  Description -> (string)

    

    A text description of the HSM configuration.

    

    

  HsmIpAddress -> (string)

    

    The IP address that the Amazon Redshift cluster must use to access the HSM.

    

    

  HsmPartitionName -> (string)

    

    The name of the partition in the HSM where the Amazon Redshift clusters will store their database encryption keys.

    

    

  Tags -> (list)

    

    The list of tags for the HSM configuration.

    

    (structure)

      

      A tag consisting of a name/value pair for a resource.

      

      Key -> (string)

        

        The key, or name, for the resource tag.

        

        

      Value -> (string)

        

        The value for the resource tag.

        

        

      

    

  



.. _Hardware Security Modules: http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-HSM.html
