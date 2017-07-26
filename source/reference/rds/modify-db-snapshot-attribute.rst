[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds modify-db-snapshot-attribute:


****************************
modify-db-snapshot-attribute
****************************



===========
Description
===========



Adds an attribute and values to, or removes an attribute and values from a manual DB snapshot.

 

To share a manual DB snapshot with other AWS accounts, specify ``restore`` as the ``AttributeName`` and use the ``ValuesToAdd`` parameter to add a list of the AWS account ids that are authorized to restore the manual DB snapshot. Uses the value ``all`` to make the manual DB snapshot public and can by copied or restored by all AWS accounts. Do not add the ``all`` value for any manual DB snapshots that contain private information that you do not want to be available to all AWS accounts.

 

To view which AWS accounts have access to copy or restore a manual DB snapshot, or whether a manual DB snapshot public or private, use the  describe-db-snapshot-attributes API.

 

If the manual DB snapshot is encrypted, it cannot be shared.



========
Synopsis
========

::

    modify-db-snapshot-attribute
  --db-snapshot-identifier <value>
  [--attribute-name <value>]
  [--values-to-add <value>]
  [--values-to-remove <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-snapshot-identifier`` (string)


  The identifier for the DB snapshot to modify the attributes for.

  

``--attribute-name`` (string)


  The name of the DB snapshot attribute to modify.

   

  To manage authorization for other AWS accounts to copy or restore a manual DB snapshot, this value is ``restore`` .

  

``--values-to-add`` (list)


  A list of DB snapshot attributes to add to the attribute specified by ``AttributeName`` .

   

  To authorize other AWS Accounts to copy or restore a manual snapshot, this is one or more AWS account identifiers, or ``all`` to make the manual DB snapshot restorable by any AWS account. Do not add the ``all`` value for any manual DB snapshots that contain private information that you do not want to be available to all AWS accounts.

  



Syntax::

  "string" "string" ...



``--values-to-remove`` (list)


  A list of DB snapshot attributes to remove from the attribute specified by ``AttributeName`` .

   

  To remove authorization for other AWS Accounts to copy or restore a manual snapshot, this is one or more AWS account identifiers, or ``all`` to remove authorization for any AWS account to copy or restore the DB snapshot. If you specify ``all`` , AWS accounts that have their account identifier explicitly added to the ``restore`` attribute can still copy or restore the manual DB snapshot.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

DBSnapshotAttributesResult -> (structure)

  

  Contains the results of a successful call to the  describe-db-snapshot-attributes API.

   

  Manual DB snapshot attributes are used to authorize other AWS accounts to copy or restore a manual DB snapshot. For more information, see the  modify-db-snapshot-attribute API.

  

  DBSnapshotIdentifier -> (string)

    

    The identifier of the manual DB snapshot that the attributes apply to.

    

    

  DBSnapshotAttributes -> (list)

    

    The list of attributes and values for the manual DB snapshot.

    

    (structure)

      

      Contains the name and values of a manual DB snapshot attribute

       

      Manual DB snapshot attributes are used to authorize other AWS accounts to restore a manual DB snapshot. For more information, see the  modify-db-snapshot-attribute API.

      

      AttributeName -> (string)

        

        The name of the manual DB snapshot attribute.

         

        An attribute name of ``restore`` applies to the list of AWS accounts that have permission to copy or restore the manual DB snapshot.

        

        

      AttributeValues -> (list)

        

        The value(s) for the manual DB snapshot attribute.

         

        If the ``AttributeName`` field is ``restore`` , then this field returns a list of AWS account ids that are authorized to copy or restore the manual DB snapshot. If a value of ``all`` is in the list, then the manual DB snapshot is public and available for any AWS account to copy or restore.

        

        (string)

          

          

        

      

    

  

