[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift describe-snapshot-copy-grants:


*****************************
describe-snapshot-copy-grants
*****************************



===========
Description
===========



Returns a list of snapshot copy grants owned by the AWS account in the destination region.

 

For more information about managing snapshot copy grants, go to `Amazon Redshift Database Encryption <http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-db-encryption.html>`_ in the *Amazon Redshift Cluster Management Guide* . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/redshift-2012-12-01/DescribeSnapshotCopyGrants>`_


========
Synopsis
========

::

    describe-snapshot-copy-grants
  [--snapshot-copy-grant-name <value>]
  [--max-records <value>]
  [--marker <value>]
  [--tag-keys <value>]
  [--tag-values <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--snapshot-copy-grant-name`` (string)


  The name of the snapshot copy grant.

  

``--max-records`` (integer)


  The maximum number of response records to return in each call. If the number of remaining response records exceeds the specified ``MaxRecords`` value, a value is returned in a ``marker`` field of the response. You can retrieve the next set of records by retrying the command with the returned marker value. 

   

  Default: ``100``  

   

  Constraints: minimum 20, maximum 100.

  

``--marker`` (string)


  An optional parameter that specifies the starting point to return a set of response records. When the results of a ``DescribeSnapshotCopyGrant`` request exceed the value specified in ``MaxRecords`` , AWS returns a value in the ``Marker`` field of the response. You can retrieve the next set of response records by providing the returned marker value in the ``Marker`` parameter and retrying the request. 

   

  Constraints: You can specify either the **SnapshotCopyGrantName** parameter or the **Marker** parameter, but not both. 

  

``--tag-keys`` (list)


  A tag key or keys for which you want to return all matching resources that are associated with the specified key or keys. For example, suppose that you have resources tagged with keys called ``owner`` and ``environment`` . If you specify both of these tag keys in the request, Amazon Redshift returns a response with all resources that have either or both of these tag keys associated with them.

  



Syntax::

  "string" "string" ...



``--tag-values`` (list)


  A tag value or values for which you want to return all matching resources that are associated with the specified value or values. For example, suppose that you have resources tagged with values called ``admin`` and ``test`` . If you specify both of these tag values in the request, Amazon Redshift returns a response with all resources that have either or both of these tag values associated with them.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Marker -> (string)

  

  An optional parameter that specifies the starting point to return a set of response records. When the results of a ``DescribeSnapshotCopyGrant`` request exceed the value specified in ``MaxRecords`` , AWS returns a value in the ``Marker`` field of the response. You can retrieve the next set of response records by providing the returned marker value in the ``Marker`` parameter and retrying the request. 

   

  Constraints: You can specify either the **SnapshotCopyGrantName** parameter or the **Marker** parameter, but not both. 

  

  

SnapshotCopyGrants -> (list)

  

  The list of ``SnapshotCopyGrant`` objects.

  

  (structure)

    

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

          

          

        

      

    

  

