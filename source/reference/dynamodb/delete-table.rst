[ :ref:`aws <cli:aws>` . :ref:`dynamodb <cli:aws dynamodb>` ]

.. _cli:aws dynamodb delete-table:


************
delete-table
************



===========
Description
===========



The ``delete-table`` operation deletes a table and all of its items. After a ``delete-table`` request, the specified table is in the ``DELETING`` state until DynamoDB completes the deletion. If the table is in the ``ACTIVE`` state, you can delete it. If a table is in ``CREATING`` or ``UPDATING`` states, then DynamoDB returns a ``ResourceInUseException`` . If the specified table does not exist, DynamoDB returns a ``ResourceNotFoundException`` . If table is already in the ``DELETING`` state, no error is returned. 

 

.. note::

   

  DynamoDB might continue to accept data read and write operations, such as ``get-item`` and ``put-item`` , on a table in the ``DELETING`` state until the table deletion is complete.

   

 

When you delete a table, any indexes on that table are also deleted.

 

If you have DynamoDB Streams enabled on the table, then the corresponding stream on that table goes into the ``DISABLED`` state, and the stream is automatically deleted after 24 hours.

 

Use the ``describe-table`` action to check the status of the table. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dynamodb-2012-08-10/DeleteTable>`_


========
Synopsis
========

::

    delete-table
  --table-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--table-name`` (string)


  The name of the table to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a table**

This example deletes the *MusicCollection* table.

Command::

  aws dynamodb delete-table --table-name MusicCollection

Output::

  {
      "TableDescription": {
          "TableStatus": "DELETING", 
          "TableSizeBytes": 0, 
          "ItemCount": 0, 
          "TableName": "MusicCollection", 
          "ProvisionedThroughput": {
              "NumberOfDecreasesToday": 0, 
              "WriteCapacityUnits": 5, 
              "ReadCapacityUnits": 5
          }
      }
  }


======
Output
======

TableDescription -> (structure)

  

  Represents the properties of a table.

  

  AttributeDefinitions -> (list)

    

    An array of ``AttributeDefinition`` objects. Each of these objects describes one attribute in the table and index key schema.

     

    Each ``AttributeDefinition`` object in this array is composed of:

     

     
    * ``AttributeName`` - The name of the attribute. 
     
    * ``AttributeType`` - The data type for the attribute. 
     

    

    (structure)

      

      Represents an attribute for describing the key schema for the table and indexes.

      

      AttributeName -> (string)

        

        A name for the attribute.

        

        

      AttributeType -> (string)

        

        The data type for the attribute, where:

         

         
        * ``S`` - the attribute is of type String 
         
        * ``N`` - the attribute is of type Number 
         
        * ``B`` - the attribute is of type Binary 
         

        

        

      

    

  TableName -> (string)

    

    The name of the table.

    

    

  KeySchema -> (list)

    

    The primary key structure for the table. Each ``KeySchemaElement`` consists of:

     

     
    * ``AttributeName`` - The name of the attribute. 
     
    * ``KeyType`` - The role of the attribute: 

       
      * ``HASH`` - partition key 
       
      * ``RANGE`` - sort key 
       

     

    .. note::

       

      The partition key of an item is also known as its *hash attribute* . The term "hash attribute" derives from DynamoDB' usage of an internal hash function to evenly distribute data items across partitions, based on their partition key values.

       

      The sort key of an item is also known as its *range attribute* . The term "range attribute" derives from the way DynamoDB stores items with the same partition key physically close together, in sorted order by the sort key value.

       

     
     

     

    For more information about primary keys, see `Primary Key <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DataModel.html#DataModelPrimaryKey>`_ in the *Amazon DynamoDB Developer Guide* .

    

    (structure)

      

      Represents *a single element* of a key schema. A key schema specifies the attributes that make up the primary key of a table, or the key attributes of an index.

       

      A ``KeySchemaElement`` represents exactly one attribute of the primary key. For example, a simple primary key would be represented by one ``KeySchemaElement`` (for the partition key). A composite primary key would require one ``KeySchemaElement`` for the partition key, and another ``KeySchemaElement`` for the sort key.

       

      A ``KeySchemaElement`` must be a scalar, top-level attribute (not a nested attribute). The data type must be one of String, Number, or Binary. The attribute cannot be nested within a List or a Map.

      

      AttributeName -> (string)

        

        The name of a key attribute.

        

        

      KeyType -> (string)

        

        The role that this key attribute will assume:

         

         
        * ``HASH`` - partition key 
         
        * ``RANGE`` - sort key 
         

         

        .. note::

           

          The partition key of an item is also known as its *hash attribute* . The term "hash attribute" derives from DynamoDB' usage of an internal hash function to evenly distribute data items across partitions, based on their partition key values.

           

          The sort key of an item is also known as its *range attribute* . The term "range attribute" derives from the way DynamoDB stores items with the same partition key physically close together, in sorted order by the sort key value.

           

        

        

      

    

  TableStatus -> (string)

    

    The current state of the table:

     

     
    * ``CREATING`` - The table is being created. 
     
    * ``UPDATING`` - The table is being updated. 
     
    * ``DELETING`` - The table is being deleted. 
     
    * ``ACTIVE`` - The table is ready for use. 
     

    

    

  CreationDateTime -> (timestamp)

    

    The date and time when the table was created, in `UNIX epoch time <http://www.epochconverter.com/>`_ format.

    

    

  ProvisionedThroughput -> (structure)

    

    The provisioned throughput settings for the table, consisting of read and write capacity units, along with data about increases and decreases.

    

    LastIncreaseDateTime -> (timestamp)

      

      The date and time of the last provisioned throughput increase for this table.

      

      

    LastDecreaseDateTime -> (timestamp)

      

      The date and time of the last provisioned throughput decrease for this table.

      

      

    NumberOfDecreasesToday -> (long)

      

      The number of provisioned throughput decreases for this table during this UTC calendar day. For current maximums on provisioned throughput decreases, see `Limits <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Limits.html>`_ in the *Amazon DynamoDB Developer Guide* .

      

      

    ReadCapacityUnits -> (long)

      

      The maximum number of strongly consistent reads consumed per second before DynamoDB returns a ``ThrottlingException`` . Eventually consistent reads require less effort than strongly consistent reads, so a setting of 50 ``ReadCapacityUnits`` per second provides 100 eventually consistent ``ReadCapacityUnits`` per second.

      

      

    WriteCapacityUnits -> (long)

      

      The maximum number of writes consumed per second before DynamoDB returns a ``ThrottlingException`` .

      

      

    

  TableSizeBytes -> (long)

    

    The total size of the specified table, in bytes. DynamoDB updates this value approximately every six hours. Recent changes might not be reflected in this value.

    

    

  ItemCount -> (long)

    

    The number of items in the specified table. DynamoDB updates this value approximately every six hours. Recent changes might not be reflected in this value.

    

    

  TableArn -> (string)

    

    The Amazon Resource Name (ARN) that uniquely identifies the table.

    

    

  LocalSecondaryIndexes -> (list)

    

    Represents one or more local secondary indexes on the table. Each index is scoped to a given partition key value. Tables with one or more local secondary indexes are subject to an item collection size limit, where the amount of data within a given item collection cannot exceed 10 GB. Each element is composed of:

     

     
    * ``IndexName`` - The name of the local secondary index. 
     
    * ``KeySchema`` - Specifies the complete index key schema. The attribute names in the key schema must be between 1 and 255 characters (inclusive). The key schema must begin with the same partition key as the table. 
     
    * ``Projection`` - Specifies attributes that are copied (projected) from the table into the index. These are in addition to the primary key attributes and index key attributes, which are automatically projected. Each attribute specification is composed of: 

       
      * ``ProjectionType`` - One of the following: 

         
        * ``KEYS_ONLY`` - Only the index and primary keys are projected into the index. 
         
        * ``INCLUDE`` - Only the specified table attributes are projected into the index. The list of projected attributes are in ``NonKeyAttributes`` . 
         
        * ``ALL`` - All of the table attributes are projected into the index. 
         

       
       
      * ``NonKeyAttributes`` - A list of one or more non-key attribute names that are projected into the secondary index. The total count of attributes provided in ``NonKeyAttributes`` , summed across all of the secondary indexes, must not exceed 20. If you project the same attribute into two different indexes, this counts as two distinct attributes when determining the total. 
       

     
     
    * ``IndexSizeBytes`` - Represents the total size of the index, in bytes. DynamoDB updates this value approximately every six hours. Recent changes might not be reflected in this value. 
     
    * ``ItemCount`` - Represents the number of items in the index. DynamoDB updates this value approximately every six hours. Recent changes might not be reflected in this value. 
     

     

    If the table is in the ``DELETING`` state, no information about indexes will be returned.

    

    (structure)

      

      Represents the properties of a local secondary index.

      

      IndexName -> (string)

        

        Represents the name of the local secondary index.

        

        

      KeySchema -> (list)

        

        The complete key schema for the local secondary index, consisting of one or more pairs of attribute names and key types:

         

         
        * ``HASH`` - partition key 
         
        * ``RANGE`` - sort key 
         

         

        .. note::

           

          The partition key of an item is also known as its *hash attribute* . The term "hash attribute" derives from DynamoDB' usage of an internal hash function to evenly distribute data items across partitions, based on their partition key values.

           

          The sort key of an item is also known as its *range attribute* . The term "range attribute" derives from the way DynamoDB stores items with the same partition key physically close together, in sorted order by the sort key value.

           

        

        (structure)

          

          Represents *a single element* of a key schema. A key schema specifies the attributes that make up the primary key of a table, or the key attributes of an index.

           

          A ``KeySchemaElement`` represents exactly one attribute of the primary key. For example, a simple primary key would be represented by one ``KeySchemaElement`` (for the partition key). A composite primary key would require one ``KeySchemaElement`` for the partition key, and another ``KeySchemaElement`` for the sort key.

           

          A ``KeySchemaElement`` must be a scalar, top-level attribute (not a nested attribute). The data type must be one of String, Number, or Binary. The attribute cannot be nested within a List or a Map.

          

          AttributeName -> (string)

            

            The name of a key attribute.

            

            

          KeyType -> (string)

            

            The role that this key attribute will assume:

             

             
            * ``HASH`` - partition key 
             
            * ``RANGE`` - sort key 
             

             

            .. note::

               

              The partition key of an item is also known as its *hash attribute* . The term "hash attribute" derives from DynamoDB' usage of an internal hash function to evenly distribute data items across partitions, based on their partition key values.

               

              The sort key of an item is also known as its *range attribute* . The term "range attribute" derives from the way DynamoDB stores items with the same partition key physically close together, in sorted order by the sort key value.

               

            

            

          

        

      Projection -> (structure)

        

        Represents attributes that are copied (projected) from the table into the global secondary index. These are in addition to the primary key attributes and index key attributes, which are automatically projected. 

        

        ProjectionType -> (string)

          

          The set of attributes that are projected into the index:

           

           
          * ``KEYS_ONLY`` - Only the index and primary keys are projected into the index. 
           
          * ``INCLUDE`` - Only the specified table attributes are projected into the index. The list of projected attributes are in ``NonKeyAttributes`` . 
           
          * ``ALL`` - All of the table attributes are projected into the index. 
           

          

          

        NonKeyAttributes -> (list)

          

          Represents the non-key attribute names which will be projected into the index.

           

          For local secondary indexes, the total count of ``NonKeyAttributes`` summed across all of the local secondary indexes, must not exceed 20. If you project the same attribute into two different indexes, this counts as two distinct attributes when determining the total.

          

          (string)

            

            

          

        

      IndexSizeBytes -> (long)

        

        The total size of the specified index, in bytes. DynamoDB updates this value approximately every six hours. Recent changes might not be reflected in this value.

        

        

      ItemCount -> (long)

        

        The number of items in the specified index. DynamoDB updates this value approximately every six hours. Recent changes might not be reflected in this value.

        

        

      IndexArn -> (string)

        

        The Amazon Resource Name (ARN) that uniquely identifies the index.

        

        

      

    

  GlobalSecondaryIndexes -> (list)

    

    The global secondary indexes, if any, on the table. Each index is scoped to a given partition key value. Each element is composed of:

     

     
    * ``Backfilling`` - If true, then the index is currently in the backfilling phase. Backfilling occurs only when a new global secondary index is added to the table; it is the process by which DynamoDB populates the new index with data from the table. (This attribute does not appear for indexes that were created during a ``create-table`` operation.) 
     
    * ``IndexName`` - The name of the global secondary index. 
     
    * ``IndexSizeBytes`` - The total size of the global secondary index, in bytes. DynamoDB updates this value approximately every six hours. Recent changes might not be reflected in this value.  
     
    * ``IndexStatus`` - The current status of the global secondary index: 

       
      * ``CREATING`` - The index is being created. 
       
      * ``UPDATING`` - The index is being updated. 
       
      * ``DELETING`` - The index is being deleted. 
       
      * ``ACTIVE`` - The index is ready for use. 
       

     
     
    * ``ItemCount`` - The number of items in the global secondary index. DynamoDB updates this value approximately every six hours. Recent changes might not be reflected in this value.  
     
    * ``KeySchema`` - Specifies the complete index key schema. The attribute names in the key schema must be between 1 and 255 characters (inclusive). The key schema must begin with the same partition key as the table. 
     
    * ``Projection`` - Specifies attributes that are copied (projected) from the table into the index. These are in addition to the primary key attributes and index key attributes, which are automatically projected. Each attribute specification is composed of: 

       
      * ``ProjectionType`` - One of the following: 

         
        * ``KEYS_ONLY`` - Only the index and primary keys are projected into the index. 
         
        * ``INCLUDE`` - Only the specified table attributes are projected into the index. The list of projected attributes are in ``NonKeyAttributes`` . 
         
        * ``ALL`` - All of the table attributes are projected into the index. 
         

       
       
      * ``NonKeyAttributes`` - A list of one or more non-key attribute names that are projected into the secondary index. The total count of attributes provided in ``NonKeyAttributes`` , summed across all of the secondary indexes, must not exceed 20. If you project the same attribute into two different indexes, this counts as two distinct attributes when determining the total. 
       

     
     
    * ``ProvisionedThroughput`` - The provisioned throughput settings for the global secondary index, consisting of read and write capacity units, along with data about increases and decreases.  
     

     

    If the table is in the ``DELETING`` state, no information about indexes will be returned.

    

    (structure)

      

      Represents the properties of a global secondary index.

      

      IndexName -> (string)

        

        The name of the global secondary index.

        

        

      KeySchema -> (list)

        

        The complete key schema for a global secondary index, which consists of one or more pairs of attribute names and key types:

         

         
        * ``HASH`` - partition key 
         
        * ``RANGE`` - sort key 
         

         

        .. note::

           

          The partition key of an item is also known as its *hash attribute* . The term "hash attribute" derives from DynamoDB' usage of an internal hash function to evenly distribute data items across partitions, based on their partition key values.

           

          The sort key of an item is also known as its *range attribute* . The term "range attribute" derives from the way DynamoDB stores items with the same partition key physically close together, in sorted order by the sort key value.

           

        

        (structure)

          

          Represents *a single element* of a key schema. A key schema specifies the attributes that make up the primary key of a table, or the key attributes of an index.

           

          A ``KeySchemaElement`` represents exactly one attribute of the primary key. For example, a simple primary key would be represented by one ``KeySchemaElement`` (for the partition key). A composite primary key would require one ``KeySchemaElement`` for the partition key, and another ``KeySchemaElement`` for the sort key.

           

          A ``KeySchemaElement`` must be a scalar, top-level attribute (not a nested attribute). The data type must be one of String, Number, or Binary. The attribute cannot be nested within a List or a Map.

          

          AttributeName -> (string)

            

            The name of a key attribute.

            

            

          KeyType -> (string)

            

            The role that this key attribute will assume:

             

             
            * ``HASH`` - partition key 
             
            * ``RANGE`` - sort key 
             

             

            .. note::

               

              The partition key of an item is also known as its *hash attribute* . The term "hash attribute" derives from DynamoDB' usage of an internal hash function to evenly distribute data items across partitions, based on their partition key values.

               

              The sort key of an item is also known as its *range attribute* . The term "range attribute" derives from the way DynamoDB stores items with the same partition key physically close together, in sorted order by the sort key value.

               

            

            

          

        

      Projection -> (structure)

        

        Represents attributes that are copied (projected) from the table into the global secondary index. These are in addition to the primary key attributes and index key attributes, which are automatically projected. 

        

        ProjectionType -> (string)

          

          The set of attributes that are projected into the index:

           

           
          * ``KEYS_ONLY`` - Only the index and primary keys are projected into the index. 
           
          * ``INCLUDE`` - Only the specified table attributes are projected into the index. The list of projected attributes are in ``NonKeyAttributes`` . 
           
          * ``ALL`` - All of the table attributes are projected into the index. 
           

          

          

        NonKeyAttributes -> (list)

          

          Represents the non-key attribute names which will be projected into the index.

           

          For local secondary indexes, the total count of ``NonKeyAttributes`` summed across all of the local secondary indexes, must not exceed 20. If you project the same attribute into two different indexes, this counts as two distinct attributes when determining the total.

          

          (string)

            

            

          

        

      IndexStatus -> (string)

        

        The current state of the global secondary index:

         

         
        * ``CREATING`` - The index is being created. 
         
        * ``UPDATING`` - The index is being updated. 
         
        * ``DELETING`` - The index is being deleted. 
         
        * ``ACTIVE`` - The index is ready for use. 
         

        

        

      Backfilling -> (boolean)

        

        Indicates whether the index is currently backfilling. *Backfilling* is the process of reading items from the table and determining whether they can be added to the index. (Not all items will qualify: For example, a partition key cannot have any duplicate values.) If an item can be added to the index, DynamoDB will do so. After all items have been processed, the backfilling operation is complete and ``Backfilling`` is false.

         

        .. note::

           

          For indexes that were created during a ``create-table`` operation, the ``Backfilling`` attribute does not appear in the ``describe-table`` output.

           

        

        

      ProvisionedThroughput -> (structure)

        

        Represents the provisioned throughput settings for the specified global secondary index.

         

        For current minimum and maximum provisioned throughput values, see `Limits <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Limits.html>`_ in the *Amazon DynamoDB Developer Guide* .

        

        LastIncreaseDateTime -> (timestamp)

          

          The date and time of the last provisioned throughput increase for this table.

          

          

        LastDecreaseDateTime -> (timestamp)

          

          The date and time of the last provisioned throughput decrease for this table.

          

          

        NumberOfDecreasesToday -> (long)

          

          The number of provisioned throughput decreases for this table during this UTC calendar day. For current maximums on provisioned throughput decreases, see `Limits <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Limits.html>`_ in the *Amazon DynamoDB Developer Guide* .

          

          

        ReadCapacityUnits -> (long)

          

          The maximum number of strongly consistent reads consumed per second before DynamoDB returns a ``ThrottlingException`` . Eventually consistent reads require less effort than strongly consistent reads, so a setting of 50 ``ReadCapacityUnits`` per second provides 100 eventually consistent ``ReadCapacityUnits`` per second.

          

          

        WriteCapacityUnits -> (long)

          

          The maximum number of writes consumed per second before DynamoDB returns a ``ThrottlingException`` .

          

          

        

      IndexSizeBytes -> (long)

        

        The total size of the specified index, in bytes. DynamoDB updates this value approximately every six hours. Recent changes might not be reflected in this value.

        

        

      ItemCount -> (long)

        

        The number of items in the specified index. DynamoDB updates this value approximately every six hours. Recent changes might not be reflected in this value.

        

        

      IndexArn -> (string)

        

        The Amazon Resource Name (ARN) that uniquely identifies the index.

        

        

      

    

  StreamSpecification -> (structure)

    

    The current DynamoDB Streams configuration for the table.

    

    StreamEnabled -> (boolean)

      

      Indicates whether DynamoDB Streams is enabled (true) or disabled (false) on the table.

      

      

    StreamViewType -> (string)

      

      When an item in the table is modified, ``StreamViewType`` determines what information is written to the stream for this table. Valid values for ``StreamViewType`` are:

       

       
      * ``KEYS_ONLY`` - Only the key attributes of the modified item are written to the stream. 
       
      * ``NEW_IMAGE`` - The entire item, as it appears after it was modified, is written to the stream. 
       
      * ``OLD_IMAGE`` - The entire item, as it appeared before it was modified, is written to the stream. 
       
      * ``NEW_AND_OLD_IMAGES`` - Both the new and the old item images of the item are written to the stream. 
       

      

      

    

  LatestStreamLabel -> (string)

    

    A timestamp, in ISO 8601 format, for this stream.

     

    Note that ``LatestStreamLabel`` is not a unique identifier for the stream, because it is possible that a stream from another table might have the same timestamp. However, the combination of the following three elements is guaranteed to be unique:

     

     
    * the AWS customer ID. 
     
    * the table name. 
     
    * the ``StreamLabel`` . 
     

    

    

  LatestStreamArn -> (string)

    

    The Amazon Resource Name (ARN) that uniquely identifies the latest stream for this table.

    

    

  

