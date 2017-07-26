[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift create-snapshot-copy-grant:


**************************
create-snapshot-copy-grant
**************************



===========
Description
===========



Creates a snapshot copy grant that permits Amazon Redshift to use a customer master key (CMK) from AWS Key Management Service (AWS KMS) to encrypt copied snapshots in a destination region.

 

For more information about managing snapshot copy grants, go to `Amazon Redshift Database Encryption <http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-db-encryption.html>`_ in the *Amazon Redshift Cluster Management Guide* . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/redshift-2012-12-01/CreateSnapshotCopyGrant>`_


========
Synopsis
========

::

    create-snapshot-copy-grant
  --snapshot-copy-grant-name <value>
  [--kms-key-id <value>]
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--snapshot-copy-grant-name`` (string)


  The name of the snapshot copy grant. This name must be unique in the region for the AWS account.

   

  Constraints:

   

   
  * Must contain from 1 to 63 alphanumeric characters or hyphens. 
   
  * Alphabetic characters must be lowercase. 
   
  * First character must be a letter. 
   
  * Cannot end with a hyphen or contain two consecutive hyphens. 
   
  * Must be unique for all clusters within an AWS account. 
   

  

``--kms-key-id`` (string)


  The unique identifier of the customer master key (CMK) to which to grant Amazon Redshift permission. If no key is specified, the default key is used.

  

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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

SnapshotCopyGrant -> (structure)

  

  The snapshot copy grant that grants Amazon Redshift permission to encrypt copied snapshots with the specified customer master key (CMK) from AWS KMS in the destination region.

   

  For more information about managing snapshot copy grants, go to `Amazon Redshift Database Encryption <http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-db-encryption.html>`_ in the *Amazon Redshift Cluster Management Guide* . 

  

  SnapshotCopyGrantName -> (string)

    

    The name of the snapshot copy grant.

    

    

  KmsKeyId -> (string)

    

    The unique identifier of the customer master key (CMK) in AWS KMS to which Amazon Redshift is granted permission.

    

    

  Tags -> (list)

    

    A list of tag instances.

    

    (structure)

      

      A tag consisting of a name/value pair for a resource.

      

      Key -> (string)

        

        The key, or name, for the resource tag.

        

        

      Value -> (string)

        

        The value for the resource tag.

        

        

      

    

  

