[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-db-cluster-snapshot-attributes:


***************************************
describe-db-cluster-snapshot-attributes
***************************************



===========
Description
===========



Returns a list of DB cluster snapshot attribute names and values for a manual DB cluster snapshot.

 

When sharing snapshots with other AWS accounts, ``describe-db-cluster-snapshot-attributes`` returns the ``restore`` attribute and a list of IDs for the AWS accounts that are authorized to copy or restore the manual DB cluster snapshot. If ``all`` is included in the list of values for the ``restore`` attribute, then the manual DB cluster snapshot is public and can be copied or restored by all AWS accounts.

 

To add or remove access for an AWS account to copy or restore a manual DB cluster snapshot, or to make the manual DB cluster snapshot public or private, use the  modify-db-cluster-snapshot-attribute API action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/DescribeDBClusterSnapshotAttributes>`_


========
Synopsis
========

::

    describe-db-cluster-snapshot-attributes
  --db-cluster-snapshot-identifier <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--db-cluster-snapshot-identifier`` (string)


  The identifier for the DB cluster snapshot to describe the attributes for.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DBClusterSnapshotAttributesResult -> (structure)

  

  Contains the results of a successful call to the  describe-db-cluster-snapshot-attributes API action.

   

  Manual DB cluster snapshot attributes are used to authorize other AWS accounts to copy or restore a manual DB cluster snapshot. For more information, see the  modify-db-cluster-snapshot-attribute API action.

  

  DBClusterSnapshotIdentifier -> (string)

    

    The identifier of the manual DB cluster snapshot that the attributes apply to.

    

    

  DBClusterSnapshotAttributes -> (list)

    

    The list of attributes and values for the manual DB cluster snapshot.

    

    (structure)

      

      Contains the name and values of a manual DB cluster snapshot attribute.

       

      Manual DB cluster snapshot attributes are used to authorize other AWS accounts to restore a manual DB cluster snapshot. For more information, see the  modify-db-cluster-snapshot-attribute API action.

      

      AttributeName -> (string)

        

        The name of the manual DB cluster snapshot attribute.

         

        The attribute named ``restore`` refers to the list of AWS accounts that have permission to copy or restore the manual DB cluster snapshot. For more information, see the  modify-db-cluster-snapshot-attribute API action.

        

        

      AttributeValues -> (list)

        

        The value(s) for the manual DB cluster snapshot attribute.

         

        If the ``AttributeName`` field is set to ``restore`` , then this element returns a list of IDs of the AWS accounts that are authorized to copy or restore the manual DB cluster snapshot. If a value of ``all`` is in the list, then the manual DB cluster snapshot is public and available for any AWS account to copy or restore.

        

        (string)

          

          

        

      

    

  

