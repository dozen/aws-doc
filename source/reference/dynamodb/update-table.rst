[ :ref:`aws <cli:aws>` . :ref:`dynamodb <cli:aws dynamodb>` ]

.. _cli:aws dynamodb update-table:


************
update-table
************



===========
Description
===========



Modifies the provisioned throughput settings, global secondary indexes, or DynamoDB Streams settings for a given table.

 

You can only perform one of the following operations at once:

 

 
* Modify the provisioned throughput settings of the table.
 
* Enable or disable Streams on the table.
 
* Remove a global secondary index from the table.
 
* Create a new global secondary index on the table. Once the index begins backfilling, you can use *update-table* to perform other operations. 
 

 

*update-table* is an asynchronous operation; while it is executing, the table status changes from ``ACTIVE`` to ``UPDATING`` . While it is ``UPDATING`` , you cannot issue another *update-table* request. When the table returns to the ``ACTIVE`` state, the *update-table* operation is complete.



========
Synopsis
========

::

    update-table
  [--attribute-definitions <value>]
  --table-name <value>
  [--provisioned-throughput <value>]
  [--global-secondary-index-updates <value>]
  [--stream-specification <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--attribute-definitions`` (list)


  An array of attributes that describe the key schema for the table and indexes. If you are adding a new global secondary index to the table, *attribute-definitions* must include the key element(s) of the new index.

  



Shorthand Syntax::

    AttributeName=string,AttributeType=string ...




JSON Syntax::

  [
    {
      "AttributeName": "string",
      "AttributeType": "S"|"N"|"B"
    }
    ...
  ]



``--table-name`` (string)


  The name of the table to be updated.

  

``--provisioned-throughput`` (structure)


  Represents the provisioned throughput settings for a specified table or index. The settings can be modified using the *update-table* operation.

   

  For current minimum and maximum provisioned throughput values, see `Limits`_ in the *Amazon DynamoDB Developer Guide* .

  



Shorthand Syntax::

    ReadCapacityUnits=long,WriteCapacityUnits=long




JSON Syntax::

  {
    "ReadCapacityUnits": long,
    "WriteCapacityUnits": long
  }



``--global-secondary-index-updates`` (list)


  An array of one or more global secondary indexes for the table. For each index in the array, you can request one action:

   

   
  * *Create* - add a new global secondary index to the table.
   
  * *Update* - modify the provisioned throughput settings of an existing global secondary index.
   
  * *Delete* - remove a global secondary index from the table.
   

   

  For more information, see `Managing Global Secondary Indexes`_ in the *Amazon DynamoDB Developer Guide* . 

  



JSON Syntax::

  [
    {
      "Update": {
        "IndexName": "string",
        "ProvisionedThroughput": {
          "ReadCapacityUnits": long,
          "WriteCapacityUnits": long
        }
      },
      "Create": {
        "IndexName": "string",
        "KeySchema": [
          {
            "AttributeName": "string",
            "KeyType": "HASH"|"RANGE"
          }
          ...
        ],
        "Projection": {
          "ProjectionType": "ALL"|"KEYS_ONLY"|"INCLUDE",
          "NonKeyAttributes": ["string", ...]
        },
        "ProvisionedThroughput": {
          "ReadCapacityUnits": long,
          "WriteCapacityUnits": long
        }
      },
      "Delete": {
        "IndexName": "string"
      }
    }
    ...
  ]



``--stream-specification`` (structure)


  Represents the DynamoDB Streams configuration for the table.

   

  .. note::

     

    You will receive a *ResourceInUseException* if you attempt to enable a stream on a table that already has a stream, or if you attempt to disable a stream on a table which does not have a stream.

     

  



Shorthand Syntax::

    StreamEnabled=boolean,StreamViewType=string




JSON Syntax::

  {
    "StreamEnabled": true|false,
    "StreamViewType": "NEW_IMAGE"|"OLD_IMAGE"|"NEW_AND_OLD_IMAGES"|"KEYS_ONLY"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To modify a table's provisioned throughput**

This example increases the provisioned read and write capacity on the *MusicCollection* table.

Command::

  aws dynamodb update-table --table-name MusicCollection --provisioned-throughput ReadCapacityUnits=10,WriteCapacityUnits=10 

Output::

  {
      "TableDescription": {
          "AttributeDefinitions": [
              {
                  "AttributeName": "Artist", 
                  "AttributeType": "S"
              }, 
              {
                  "AttributeName": "SongTitle", 
                  "AttributeType": "S"
              }
          ], 
          "ProvisionedThroughput": {
              "NumberOfDecreasesToday": 0, 
              "WriteCapacityUnits": 1, 
              "LastIncreaseDateTime": 1421874759.194, 
              "ReadCapacityUnits": 1
          }, 
          "TableSizeBytes": 0, 
          "TableName": "MusicCollection", 
          "TableStatus": "UPDATING", 
          "KeySchema": [
              {
                  "KeyType": "HASH", 
                  "AttributeName": "Artist"
              }, 
              {
                  "KeyType": "RANGE", 
                  "AttributeName": "SongTitle"
              }
          ], 
          "ItemCount": 0, 
          "CreationDateTime": 1421866952.062
      }
  }


======
Output
======

TableDescription -> (structure)

  

  Represents the properties of a table.

  

  AttributeDefinitions -> (list)

    

    An array of *AttributeDefinition* objects. Each of these objects describes one attribute in the table and index key schema.

     

    Each *AttributeDefinition* object in this array is composed of:

     

     
    * *AttributeName* - The name of the attribute. 
     
    * *AttributeType* - The data type for the attribute. 
     

    

    (structure)

      

      Represents an attribute for describing the key schema for the table and indexes.

      

      AttributeName -> (string)

        

        A name for the attribute.

        

        

      AttributeType -> (string)

        

        The data type for the attribute.

        

        

      

    

  TableName -> (string)

    

    The name of the table.

    

    

  KeySchema -> (list)

    

    The primary key structure for the table. Each *KeySchemaElement* consists of:

     

     
    * *AttributeName* - The name of the attribute. 
     
    * *KeyType* - The key type for the attribute. Can be either ``HASH`` or ``RANGE`` . 
     

     

    For more information about primary keys, see `Primary Key`_ in the *Amazon DynamoDB Developer Guide* .

    

    (structure)

      

      Represents *a single element* of a key schema. A key schema specifies the attributes that make up the primary key of a table, or the key attributes of an index.

       

      A *KeySchemaElement* represents exactly one attribute of the primary key. For example, a hash type primary key would be represented by one *KeySchemaElement* . A hash-and-range type primary key would require one *KeySchemaElement* for the hash attribute, and another *KeySchemaElement* for the range attribute.

      

      AttributeName -> (string)

        

        The name of a key attribute.

        

        

      KeyType -> (string)

        

        The attribute data, consisting of the data type and the attribute value itself.

        

        

      

    

  TableStatus -> (string)

    

    The current state of the table:

     

     
    * *CREATING* - The table is being created. 
     
    * *UPDATING* - The table is being updated. 
     
    * *DELETING* - The table is being deleted. 
     
    * *ACTIVE* - The table is ready for use. 
     

    

    

  CreationDateTime -> (timestamp)

    

    The date and time when the table was created, in `UNIX epoch time`_ format.

    

    

  ProvisionedThroughput -> (structure)

    

    The provisioned throughput settings for the table, consisting of read and write capacity units, along with data about increases and decreases.

    

    LastIncreaseDateTime -> (timestamp)

      

      The date and time of the last provisioned throughput increase for this table.

      

      

    LastDecreaseDateTime -> (timestamp)

      

      The date and time of the last provisioned throughput decrease for this table.

      

      

    NumberOfDecreasesToday -> (long)

      

      The number of provisioned throughput decreases for this table during this UTC calendar day. For current maximums on provisioned throughput decreases, see `Limits`_ in the *Amazon DynamoDB Developer Guide* .

      

      

    ReadCapacityUnits -> (long)

      

      The maximum number of strongly consistent reads consumed per second before DynamoDB returns a *ThrottlingException* . Eventually consistent reads require less effort than strongly consistent reads, so a setting of 50 *ReadCapacityUnits* per second provides 100 eventually consistent *ReadCapacityUnits* per second.

      

      

    WriteCapacityUnits -> (long)

      

      The maximum number of writes consumed per second before DynamoDB returns a *ThrottlingException* .

      

      

    

  TableSizeBytes -> (long)

    

    The total size of the specified table, in bytes. DynamoDB updates this value approximately every six hours. Recent changes might not be reflected in this value. 

    

    

  ItemCount -> (long)

    

    The number of items in the specified table. DynamoDB updates this value approximately every six hours. Recent changes might not be reflected in this value. 

    

    

  TableArn -> (string)

    

    The Amazon Resource Name (ARN) that uniquely identifies the table.

    

    

  LocalSecondaryIndexes -> (list)

    

    Represents one or more local secondary indexes on the table. Each index is scoped to a given hash key value. Tables with one or more local secondary indexes are subject to an item collection size limit, where the amount of data within a given item collection cannot exceed 10 GB. Each element is composed of:

     

     
    * *IndexName* - The name of the local secondary index. 
     
    * *KeySchema* - Specifies the complete index key schema. The attribute names in the key schema must be between 1 and 255 characters (inclusive). The key schema must begin with the same hash key attribute as the table. 
     
    * *Projection* - Specifies attributes that are copied (projected) from the table into the index. These are in addition to the primary key attributes and index key attributes, which are automatically projected. Each attribute specification is composed of: 

       
      * *ProjectionType* - One of the following: 

         
        * ``KEYS_ONLY`` - Only the index and primary keys are projected into the index. 
         
        * ``INCLUDE`` - Only the specified table attributes are projected into the index. The list of projected attributes are in *NonKeyAttributes* . 
         
        * ``ALL`` - All of the table attributes are projected into the index. 
         

       
       
      * *NonKeyAttributes* - A list of one or more non-key attribute names that are projected into the secondary index. The total count of attributes provided in *NonKeyAttributes* , summed across all of the secondary indexes, must not exceed 20. If you project the same attribute into two different indexes, this counts as two distinct attributes when determining the total. 
       

     
     
    * *IndexSizeBytes* - Represents the total size of the index, in bytes. DynamoDB updates this value approximately every six hours. Recent changes might not be reflected in this value. 
     
    * *ItemCount* - Represents the number of items in the index. DynamoDB updates this value approximately every six hours. Recent changes might not be reflected in this value. 
     

     

    If the table is in the ``DELETING`` state, no information about indexes will be returned.

    

    (structure)

      

      Represents the properties of a local secondary index.

      

      IndexName -> (string)

        

        Represents the name of the local secondary index.

        

        

      KeySchema -> (list)

        

        The complete index key schema, which consists of one or more pairs of attribute names and key types (``HASH`` or ``RANGE`` ).

        

        (structure)

          

          Represents *a single element* of a key schema. A key schema specifies the attributes that make up the primary key of a table, or the key attributes of an index.

           

          A *KeySchemaElement* represents exactly one attribute of the primary key. For example, a hash type primary key would be represented by one *KeySchemaElement* . A hash-and-range type primary key would require one *KeySchemaElement* for the hash attribute, and another *KeySchemaElement* for the range attribute.

          

          AttributeName -> (string)

            

            The name of a key attribute.

            

            

          KeyType -> (string)

            

            The attribute data, consisting of the data type and the attribute value itself.

            

            

          

        

      Projection -> (structure)

        

        Represents attributes that are copied (projected) from the table into an index. These are in addition to the primary key attributes and index key attributes, which are automatically projected.

        

        ProjectionType -> (string)

          

          The set of attributes that are projected into the index:

           

           
          * ``KEYS_ONLY`` - Only the index and primary keys are projected into the index. 
           
          * ``INCLUDE`` - Only the specified table attributes are projected into the index. The list of projected attributes are in *NonKeyAttributes* . 
           
          * ``ALL`` - All of the table attributes are projected into the index. 
           

          

          

        NonKeyAttributes -> (list)

          

          Represents the non-key attribute names which will be projected into the index.

           

          For local secondary indexes, the total count of *NonKeyAttributes* summed across all of the local secondary indexes, must not exceed 20. If you project the same attribute into two different indexes, this counts as two distinct attributes when determining the total.

          

          (string)

            

            

          

        

      IndexSizeBytes -> (long)

        

        The total size of the specified index, in bytes. DynamoDB updates this value approximately every six hours. Recent changes might not be reflected in this value. 

        

        

      ItemCount -> (long)

        

        The number of items in the specified index. DynamoDB updates this value approximately every six hours. Recent changes might not be reflected in this value. 

        

        

      IndexArn -> (string)

        

        The Amazon Resource Name (ARN) that uniquely identifies the index.

        

        

      

    

  GlobalSecondaryIndexes -> (list)

    

    The global secondary indexes, if any, on the table. Each index is scoped to a given hash key value. Each element is composed of:

     

     
    * *Backfilling* - If true, then the index is currently in the backfilling phase. Backfilling occurs only when a new global secondary index is added to the table; it is the process by which DynamoDB populates the new index with data from the table. (This attribute does not appear for indexes that were created during a *create-table* operation.) 
     
    * *IndexName* - The name of the global secondary index. 
     
    * *IndexSizeBytes* - The total size of the global secondary index, in bytes. DynamoDB updates this value approximately every six hours. Recent changes might not be reflected in this value.  
     
    * *IndexStatus* - The current status of the global secondary index: 

       
      * *CREATING* - The index is being created. 
       
      * *UPDATING* - The index is being updated. 
       
      * *DELETING* - The index is being deleted. 
       
      * *ACTIVE* - The index is ready for use. 
       

     
     
    * *ItemCount* - The number of items in the global secondary index. DynamoDB updates this value approximately every six hours. Recent changes might not be reflected in this value.  
     
    * *KeySchema* - Specifies the complete index key schema. The attribute names in the key schema must be between 1 and 255 characters (inclusive). The key schema must begin with the same hash key attribute as the table. 
     
    * *Projection* - Specifies attributes that are copied (projected) from the table into the index. These are in addition to the primary key attributes and index key attributes, which are automatically projected. Each attribute specification is composed of: 

       
      * *ProjectionType* - One of the following: 

         
        * ``KEYS_ONLY`` - Only the index and primary keys are projected into the index. 
         
        * ``INCLUDE`` - Only the specified table attributes are projected into the index. The list of projected attributes are in *NonKeyAttributes* . 
         
        * ``ALL`` - All of the table attributes are projected into the index. 
         

       
       
      * *NonKeyAttributes* - A list of one or more non-key attribute names that are projected into the secondary index. The total count of attributes provided in *NonKeyAttributes* , summed across all of the secondary indexes, must not exceed 20. If you project the same attribute into two different indexes, this counts as two distinct attributes when determining the total. 
       

     
     
    * *provisioned-throughput* - The provisioned throughput settings for the global secondary index, consisting of read and write capacity units, along with data about increases and decreases.  
     

     

    If the table is in the ``DELETING`` state, no information about indexes will be returned.

    

    (structure)

      

      Represents the properties of a global secondary index.

      

      IndexName -> (string)

        

        The name of the global secondary index.

        

        

      KeySchema -> (list)

        

        The complete key schema for the global secondary index, consisting of one or more pairs of attribute names and key types (``HASH`` or ``RANGE`` ).

        

        (structure)

          

          Represents *a single element* of a key schema. A key schema specifies the attributes that make up the primary key of a table, or the key attributes of an index.

           

          A *KeySchemaElement* represents exactly one attribute of the primary key. For example, a hash type primary key would be represented by one *KeySchemaElement* . A hash-and-range type primary key would require one *KeySchemaElement* for the hash attribute, and another *KeySchemaElement* for the range attribute.

          

          AttributeName -> (string)

            

            The name of a key attribute.

            

            

          KeyType -> (string)

            

            The attribute data, consisting of the data type and the attribute value itself.

            

            

          

        

      Projection -> (structure)

        

        Represents attributes that are copied (projected) from the table into an index. These are in addition to the primary key attributes and index key attributes, which are automatically projected.

        

        ProjectionType -> (string)

          

          The set of attributes that are projected into the index:

           

           
          * ``KEYS_ONLY`` - Only the index and primary keys are projected into the index. 
           
          * ``INCLUDE`` - Only the specified table attributes are projected into the index. The list of projected attributes are in *NonKeyAttributes* . 
           
          * ``ALL`` - All of the table attributes are projected into the index. 
           

          

          

        NonKeyAttributes -> (list)

          

          Represents the non-key attribute names which will be projected into the index.

           

          For local secondary indexes, the total count of *NonKeyAttributes* summed across all of the local secondary indexes, must not exceed 20. If you project the same attribute into two different indexes, this counts as two distinct attributes when determining the total.

          

          (string)

            

            

          

        

      IndexStatus -> (string)

        

        The current state of the global secondary index:

         

         
        * *CREATING* - The index is being created. 
         
        * *UPDATING* - The index is being updated. 
         
        * *DELETING* - The index is being deleted. 
         
        * *ACTIVE* - The index is ready for use. 
         

        

        

      Backfilling -> (boolean)

        

        Indicates whether the index is currently backfilling. *Backfilling* is the process of reading items from the table and determining whether they can be added to the index. (Not all items will qualify: For example, a hash key attribute cannot have any duplicates.) If an item can be added to the index, DynamoDB will do so. After all items have been processed, the backfilling operation is complete and *Backfilling* is false.

         

        .. note::

          

          For indexes that were created during a *create-table* operation, the *Backfilling* attribute does not appear in the *describe-table* output.

          

        

        

      ProvisionedThroughput -> (structure)

        

        Represents the provisioned throughput settings for the table, consisting of read and write capacity units, along with data about increases and decreases.

        

        LastIncreaseDateTime -> (timestamp)

          

          The date and time of the last provisioned throughput increase for this table.

          

          

        LastDecreaseDateTime -> (timestamp)

          

          The date and time of the last provisioned throughput decrease for this table.

          

          

        NumberOfDecreasesToday -> (long)

          

          The number of provisioned throughput decreases for this table during this UTC calendar day. For current maximums on provisioned throughput decreases, see `Limits`_ in the *Amazon DynamoDB Developer Guide* .

          

          

        ReadCapacityUnits -> (long)

          

          The maximum number of strongly consistent reads consumed per second before DynamoDB returns a *ThrottlingException* . Eventually consistent reads require less effort than strongly consistent reads, so a setting of 50 *ReadCapacityUnits* per second provides 100 eventually consistent *ReadCapacityUnits* per second.

          

          

        WriteCapacityUnits -> (long)

          

          The maximum number of writes consumed per second before DynamoDB returns a *ThrottlingException* .

          

          

        

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

      

      The DynamoDB Streams settings for the table. These settings consist of:

       

       
      * *StreamEnabled* - Indicates whether DynamoDB Streams is enabled (true) or disabled (false) on the table. 
       
      * *StreamViewType* - When an item in the table is modified, *StreamViewType* determines what information is written to the stream for this table. Valid values for *StreamViewType* are: 

         
        * *KEYS_ONLY* - Only the key attributes of the modified item are written to the stream.
         
        * *NEW_IMAGE* - The entire item, as it appears after it was modified, is written to the stream.
         
        * *OLD_IMAGE* - The entire item, as it appeared before it was modified, is written to the stream.
         
        * *NEW_AND_OLD_IMAGES* - Both the new and the old item images of the item are written to the stream.
         

       
       

      

      

    

  LatestStreamLabel -> (string)

    

    A timestamp, in ISO 8601 format, for this stream.

     

    Note that *LatestStreamLabel* is not a unique identifier for the stream, because it is possible that a stream from another table might have the same timestamp. However, the combination of the following three elements is guaranteed to be unique:

     

     
    * the AWS customer ID.
     
    * the table name.
     
    * the *StreamLabel* .
     

    

    

  LatestStreamArn -> (string)

    

    The Amazon Resource Name (ARN) that uniquely identifies the latest stream for this table.

    

    

  



.. _Primary Key: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DataModel.html#DataModelPrimaryKey
.. _UNIX epoch time: http://www.epochconverter.com/
.. _Managing Global Secondary Indexes: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/GSI.OnlineOps.html
.. _Limits: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Limits.html
