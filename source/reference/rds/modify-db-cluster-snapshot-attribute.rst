[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds modify-db-cluster-snapshot-attribute:


************************************
modify-db-cluster-snapshot-attribute
************************************



===========
Description
===========



Adds an attribute and values to, or removes an attribute and values from, a manual DB cluster snapshot.

 

To share a manual DB cluster snapshot with other AWS accounts, specify ``restore`` as the ``AttributeName`` and use the ``ValuesToAdd`` parameter to add a list of IDs of the AWS accounts that are authorized to restore the manual DB cluster snapshot. Use the value ``all`` to make the manual DB cluster snapshot public, which means that it can be copied or restored by all AWS accounts. Do not add the ``all`` value for any manual DB cluster snapshots that contain private information that you don't want available to all AWS accounts. If a manual DB cluster snapshot is encrypted, it can be shared, but only by specifying a list of authorized AWS account IDs for the ``ValuesToAdd`` parameter. You can't use ``all`` as a value for that parameter in this case.

 

To view which AWS accounts have access to copy or restore a manual DB cluster snapshot, or whether a manual DB cluster snapshot public or private, use the  describe-db-cluster-snapshot-attributes API action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/ModifyDBClusterSnapshotAttribute>`_


========
Synopsis
========

::

    modify-db-cluster-snapshot-attribute
  --db-cluster-snapshot-identifier <value>
  --attribute-name <value>
  [--values-to-add <value>]
  [--values-to-remove <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--db-cluster-snapshot-identifier`` (string)


  The identifier for the DB cluster snapshot to modify the attributes for.

  

``--attribute-name`` (string)


  The name of the DB cluster snapshot attribute to modify.

   

  To manage authorization for other AWS accounts to copy or restore a manual DB cluster snapshot, set this value to ``restore`` .

  

``--values-to-add`` (list)


  A list of DB cluster snapshot attributes to add to the attribute specified by ``AttributeName`` .

   

  To authorize other AWS accounts to copy or restore a manual DB cluster snapshot, set this list to include one or more AWS account IDs, or ``all`` to make the manual DB cluster snapshot restorable by any AWS account. Do not add the ``all`` value for any manual DB cluster snapshots that contain private information that you don't want available to all AWS accounts.

  



Syntax::

  "string" "string" ...



``--values-to-remove`` (list)


  A list of DB cluster snapshot attributes to remove from the attribute specified by ``AttributeName`` .

   

  To remove authorization for other AWS accounts to copy or restore a manual DB cluster snapshot, set this list to include one or more AWS account identifiers, or ``all`` to remove authorization for any AWS account to copy or restore the DB cluster snapshot. If you specify ``all`` , an AWS account whose account ID is explicitly added to the ``restore`` attribute can still copy or restore a manual DB cluster snapshot.

  



Syntax::

  "string" "string" ...



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

          

          

        

      

    

  

