[ :ref:`aws <cli:aws>` . :ref:`dynamodb <cli:aws dynamodb>` ]

.. _cli:aws dynamodb batch-get-item:


**************
batch-get-item
**************



===========
Description
===========



The *batch-get-item* operation returns the attributes of one or more items from one or more tables. You identify requested items by primary key.

 

A single operation can retrieve up to 16 MB of data, which can contain as many as 100 items. *batch-get-item* will return a partial result if the response size limit is exceeded, the table's provisioned throughput is exceeded, or an internal processing failure occurs. If a partial result is returned, the operation returns a value for *UnprocessedKeys* . You can use this value to retry the operation starting with the next item to get.

 

.. warning::

  

  If you request more than 100 items *batch-get-item* will return a *ValidationException* with the message "Too many items requested for the batch-get-item call".

  

 

For example, if you ask to retrieve 100 items, but each individual item is 300 KB in size, the system returns 52 items (so as not to exceed the 16 MB limit). It also returns an appropriate *UnprocessedKeys* value so you can get the next page of results. If desired, your application can include its own logic to assemble the pages of results into one data set.

 

If *none* of the items can be processed due to insufficient provisioned throughput on all of the tables in the request, then *batch-get-item* will return a *ProvisionedThroughputExceededException* . If *at least one* of the items is successfully processed, then *batch-get-item* completes successfully, while returning the keys of the unread items in *UnprocessedKeys* .

 

.. warning::

   

  If DynamoDB returns any unprocessed items, you should retry the batch operation on those items. However, *we strongly recommend that you use an exponential backoff algorithm* . If you retry the batch operation immediately, the underlying read or write requests can still fail due to throttling on the individual tables. If you delay the batch operation using exponential backoff, the individual requests in the batch are much more likely to succeed.

   

  For more information, see `Batch Operations and Error Handling`_ in the *Amazon DynamoDB Developer Guide* .

   

 

By default, *batch-get-item* performs eventually consistent reads on every table in the request. If you want strongly consistent reads instead, you can set *ConsistentRead* to ``true`` for any or all tables.

 

In order to minimize response latency, *batch-get-item* retrieves items in parallel.

 

When designing your application, keep in mind that DynamoDB does not return attributes in any particular order. To help parse the response by item, include the primary key values for the items in your request in the *AttributesToGet* parameter.

 

If a requested item does not exist, it is not returned in the result. Requests for nonexistent items consume the minimum read capacity units according to the type of read. For more information, see `Capacity Units Calculations`_ in the *Amazon DynamoDB Developer Guide* .



========
Synopsis
========

::

    batch-get-item
  --request-items <value>
  [--return-consumed-capacity <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--request-items`` (map)


  A map of one or more table names and, for each table, a map that describes one or more items to retrieve from that table. Each table name can be used only once per *batch-get-item* request.

   

  Each element in the map of items to retrieve consists of the following:

   

   
  * *ConsistentRead* - If ``true`` , a strongly consistent read is used; if ``false`` (the default), an eventually consistent read is used. 
   
  * *ExpressionAttributeNames* - One or more substitution tokens for attribute names in the *ProjectionExpression* parameter. The following are some use cases for using *ExpressionAttributeNames* : 

     
    * To access an attribute whose name conflicts with a DynamoDB reserved word. 
     
    * To create a placeholder for repeating occurrences of an attribute name in an expression. 
     
    * To prevent special characters in an attribute name from being misinterpreted in an expression. 
     

   

  Use the **#** character in an expression to dereference an attribute name. For example, consider the following attribute name:

   

    
    * ``Percentile`` 
    

   

  The name of this attribute conflicts with a reserved word, so it cannot be used directly in an expression. (For the complete list of reserved words, see `Reserved Words`_ in the *Amazon DynamoDB Developer Guide* ). To work around this, you could specify the following for *ExpressionAttributeNames* :

   

    
    * ``{"#P":"Percentile"}`` 
    

   

  You could then use this substitution in an expression, as in this example:

   

    
    * ``#P = :val`` 
    

   

  .. note::

    

    Tokens that begin with the **:** character are *expression attribute values* , which are placeholders for the actual value at runtime.

    

   

  For more information on expression attribute names, see `Accessing Item Attributes`_ in the *Amazon DynamoDB Developer Guide* .

   
   
  * *Keys* - An array of primary key attribute values that define specific items in the table. For each primary key, you must provide *all* of the key attributes. For example, with a hash type primary key, you only need to provide the hash attribute. For a hash-and-range type primary key, you must provide *both* the hash attribute and the range attribute. 
   
  * *ProjectionExpression* - A string that identifies one or more attributes to retrieve from the table. These attributes can include scalars, sets, or elements of a JSON document. The attributes in the expression must be separated by commas. If no attribute names are specified, then all attributes will be returned. If any of the requested attributes are not found, they will not appear in the result. For more information, see `Accessing Item Attributes`_ in the *Amazon DynamoDB Developer Guide* . 
   
  * *AttributesToGet* -  

  .. warning::

     This is a legacy parameter, for backward compatibility. New applications should use *ProjectionExpression* instead. Do not combine legacy parameters and expression parameters in a single API call; otherwise, DynamoDB will return a *ValidationException* exception. This parameter allows you to retrieve attributes of type List or Map; however, it cannot retrieve individual elements within a List or a Map.

   The names of one or more attributes to retrieve. If no attribute names are provided, then all attributes will be returned. If any of the requested attributes are not found, they will not appear in the result. Note that *AttributesToGet* has no effect on provisioned throughput consumption. DynamoDB determines capacity units consumed based on item size, not on the amount of data that is returned to an application. 
   

  



JSON Syntax::

  {"string": {
        "Keys": [
          {"string": {
                "S": "string",
                "N": "string",
                "B": blob,
                "SS": ["string", ...],
                "NS": ["string", ...],
                "BS": [blob, ...],
                "M": {"string": {
                      "S": "string",
                      "N": "string",
                      "B": blob,
                      "SS": ["string", ...],
                      "NS": ["string", ...],
                      "BS": [blob, ...],
                      "M": {"string": { ... recursive ... }
                        ...},
                      "L": [
                        { ... recursive ... }
                        ...
                      ],
                      "NULL": true|false,
                      "BOOL": true|false
                    }
                  ...},
                "L": [
                  {
                    "S": "string",
                    "N": "string",
                    "B": blob,
                    "SS": ["string", ...],
                    "NS": ["string", ...],
                    "BS": [blob, ...],
                    "M": {"string": { ... recursive ... }
                      ...},
                    "L": [
                      { ... recursive ... }
                      ...
                    ],
                    "NULL": true|false,
                    "BOOL": true|false
                  }
                  ...
                ],
                "NULL": true|false,
                "BOOL": true|false
              }
            ...}
          ...
        ],
        "AttributesToGet": ["string", ...],
        "ConsistentRead": true|false,
        "ProjectionExpression": "string",
        "ExpressionAttributeNames": {"string": "string"
          ...}
      }
    ...}



``--return-consumed-capacity`` (string)


  Determines the level of detail about provisioned throughput consumption that is returned in the response:

   

   
  * *INDEXES* - The response includes the aggregate *ConsumedCapacity* for the operation, together with *ConsumedCapacity* for each table and secondary index that was accessed. Note that some operations, such as *get-item* and *batch-get-item* , do not access any indexes at all. In these cases, specifying *INDEXES* will only return *ConsumedCapacity* information for table(s). 
   
  * *TOTAL* - The response includes only the aggregate *ConsumedCapacity* for the operation.
   
  * *NONE* - No *ConsumedCapacity* details are included in the response.
   

  

  Possible values:

  
  *   ``INDEXES``

  
  *   ``TOTAL``

  
  *   ``NONE``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To retrieve multiple items from a table**

This example reads multiple items from the *MusicCollection* table using a batch of three GetItem requests.  Only the *AlbumTitle* attribute is returned.

Command::

  aws dynamodb batch-get-item --request-items file://request-items.json

The arguments for ``--request-items`` are stored in a JSON file, ``request-items.json``.  Here are the contents of that file::

  {
      "MusicCollection": {
          "Keys": [
              {
                  "Artist": {"S": "No One You Know"},
                  "SongTitle": {"S": "Call Me Today"}
              },
              {
                  "Artist": {"S": "Acme Band"},
                  "SongTitle": {"S": "Happy Day"}
              },
              {
                  "Artist": {"S": "No One You Know"},
                  "SongTitle": {"S": "Scared of My Shadow"}
              }
          ],
          "ProjectionExpression":"AlbumTitle"
      }
  }

Output::

  {
      "UnprocessedKeys": {}, 
      "Responses": {
          "MusicCollection": [
              {
                  "AlbumTitle": {
                      "S": "Somewhat Famous"
                  }
              }, 
              {
                  "AlbumTitle": {
                      "S": "Blue Sky Blues"
                  }
              }, 
              {
                  "AlbumTitle": {
                      "S": "Louder Than Ever"
                  }
              }
          ]
      }
  }


======
Output
======

Responses -> (map)

  

  A map of table name to a list of items. Each object in *Responses* consists of a table name, along with a map of attribute data consisting of the data type and attribute value.

  

  key -> (string)

    

    

  value -> (list)

    

    (map)

      

      key -> (string)

        

        

      value -> (structure)

        

        Represents the data for an attribute. You can set one, and only one, of the elements.

         

        Each attribute in an item is a name-value pair. An attribute can be single-valued or multi-valued set. For example, a book item can have title and authors attributes. Each book has one title but can have many authors. The multi-valued attribute is a set; duplicate values are not allowed. 

        

        S -> (string)

          

          A String data type.

          

          

        N -> (string)

          

          A Number data type.

          

          

        B -> (blob)

          

          A Binary data type.

          

          

        SS -> (list)

          

          A String Set data type.

          

          (string)

            

            

          

        NS -> (list)

          

          A Number Set data type.

          

          (string)

            

            

          

        BS -> (list)

          

          A Binary Set data type.

          

          (blob)

            

            

          

        M -> (map)

          

          A Map of attribute values.

          

          key -> (string)

            

            

          value -> (structure)

            

            Represents the data for an attribute. You can set one, and only one, of the elements.

             

            Each attribute in an item is a name-value pair. An attribute can be single-valued or multi-valued set. For example, a book item can have title and authors attributes. Each book has one title but can have many authors. The multi-valued attribute is a set; duplicate values are not allowed. 

            

            S -> (string)

              

              A String data type.

              

              

            N -> (string)

              

              A Number data type.

              

              

            B -> (blob)

              

              A Binary data type.

              

              

            SS -> (list)

              

              A String Set data type.

              

              (string)

                

                

              

            NS -> (list)

              

              A Number Set data type.

              

              (string)

                

                

              

            BS -> (list)

              

              A Binary Set data type.

              

              (blob)

                

                

              

            M -> (map)

              

              A Map of attribute values.

              

              key -> (string)

                

                

              ( ... recursive ... )

            L -> (list)

              

              A List of attribute values.

              

              ( ... recursive ... )

            NULL -> (boolean)

              

              A Null data type.

              

              

            BOOL -> (boolean)

              

              A Boolean data type.

              

              

            

          

        L -> (list)

          

          A List of attribute values.

          

          (structure)

            

            Represents the data for an attribute. You can set one, and only one, of the elements.

             

            Each attribute in an item is a name-value pair. An attribute can be single-valued or multi-valued set. For example, a book item can have title and authors attributes. Each book has one title but can have many authors. The multi-valued attribute is a set; duplicate values are not allowed. 

            

            S -> (string)

              

              A String data type.

              

              

            N -> (string)

              

              A Number data type.

              

              

            B -> (blob)

              

              A Binary data type.

              

              

            SS -> (list)

              

              A String Set data type.

              

              (string)

                

                

              

            NS -> (list)

              

              A Number Set data type.

              

              (string)

                

                

              

            BS -> (list)

              

              A Binary Set data type.

              

              (blob)

                

                

              

            M -> (map)

              

              A Map of attribute values.

              

              key -> (string)

                

                

              ( ... recursive ... )

            L -> (list)

              

              A List of attribute values.

              

              ( ... recursive ... )

            NULL -> (boolean)

              

              A Null data type.

              

              

            BOOL -> (boolean)

              

              A Boolean data type.

              

              

            

          

        NULL -> (boolean)

          

          A Null data type.

          

          

        BOOL -> (boolean)

          

          A Boolean data type.

          

          

        

      

    

  

UnprocessedKeys -> (map)

  

  A map of tables and their respective keys that were not processed with the current response. The *UnprocessedKeys* value is in the same form as *RequestItems* , so the value can be provided directly to a subsequent *batch-get-item* operation. For more information, see *RequestItems* in the Request Parameters section.

   

  Each element consists of:

   

   
  * *Keys* - An array of primary key attribute values that define specific items in the table. 
   
  * *AttributesToGet* - One or more attributes to be retrieved from the table or index. By default, all attributes are returned. If a requested attribute is not found, it does not appear in the result. 
   
  * *ConsistentRead* - The consistency of a read operation. If set to ``true`` , then a strongly consistent read is used; otherwise, an eventually consistent read is used. 
   

   

  If there are no unprocessed keys remaining, the response contains an empty *UnprocessedKeys* map.

  

  key -> (string)

    

    

  value -> (structure)

    

    Represents a set of primary keys and, for each key, the attributes to retrieve from the table.

     

    For each primary key, you must provide *all* of the key attributes. For example, with a hash type primary key, you only need to provide the hash attribute. For a hash-and-range type primary key, you must provide *both* the hash attribute and the range attribute.

    

    Keys -> (list)

      

      The primary key attribute values that define the items and the attributes associated with the items.

      

      (map)

        

        key -> (string)

          

          

        value -> (structure)

          

          Represents the data for an attribute. You can set one, and only one, of the elements.

           

          Each attribute in an item is a name-value pair. An attribute can be single-valued or multi-valued set. For example, a book item can have title and authors attributes. Each book has one title but can have many authors. The multi-valued attribute is a set; duplicate values are not allowed. 

          

          S -> (string)

            

            A String data type.

            

            

          N -> (string)

            

            A Number data type.

            

            

          B -> (blob)

            

            A Binary data type.

            

            

          SS -> (list)

            

            A String Set data type.

            

            (string)

              

              

            

          NS -> (list)

            

            A Number Set data type.

            

            (string)

              

              

            

          BS -> (list)

            

            A Binary Set data type.

            

            (blob)

              

              

            

          M -> (map)

            

            A Map of attribute values.

            

            key -> (string)

              

              

            value -> (structure)

              

              Represents the data for an attribute. You can set one, and only one, of the elements.

               

              Each attribute in an item is a name-value pair. An attribute can be single-valued or multi-valued set. For example, a book item can have title and authors attributes. Each book has one title but can have many authors. The multi-valued attribute is a set; duplicate values are not allowed. 

              

              S -> (string)

                

                A String data type.

                

                

              N -> (string)

                

                A Number data type.

                

                

              B -> (blob)

                

                A Binary data type.

                

                

              SS -> (list)

                

                A String Set data type.

                

                (string)

                  

                  

                

              NS -> (list)

                

                A Number Set data type.

                

                (string)

                  

                  

                

              BS -> (list)

                

                A Binary Set data type.

                

                (blob)

                  

                  

                

              M -> (map)

                

                A Map of attribute values.

                

                key -> (string)

                  

                  

                ( ... recursive ... )

              L -> (list)

                

                A List of attribute values.

                

                ( ... recursive ... )

              NULL -> (boolean)

                

                A Null data type.

                

                

              BOOL -> (boolean)

                

                A Boolean data type.

                

                

              

            

          L -> (list)

            

            A List of attribute values.

            

            (structure)

              

              Represents the data for an attribute. You can set one, and only one, of the elements.

               

              Each attribute in an item is a name-value pair. An attribute can be single-valued or multi-valued set. For example, a book item can have title and authors attributes. Each book has one title but can have many authors. The multi-valued attribute is a set; duplicate values are not allowed. 

              

              S -> (string)

                

                A String data type.

                

                

              N -> (string)

                

                A Number data type.

                

                

              B -> (blob)

                

                A Binary data type.

                

                

              SS -> (list)

                

                A String Set data type.

                

                (string)

                  

                  

                

              NS -> (list)

                

                A Number Set data type.

                

                (string)

                  

                  

                

              BS -> (list)

                

                A Binary Set data type.

                

                (blob)

                  

                  

                

              M -> (map)

                

                A Map of attribute values.

                

                key -> (string)

                  

                  

                ( ... recursive ... )

              L -> (list)

                

                A List of attribute values.

                

                ( ... recursive ... )

              NULL -> (boolean)

                

                A Null data type.

                

                

              BOOL -> (boolean)

                

                A Boolean data type.

                

                

              

            

          NULL -> (boolean)

            

            A Null data type.

            

            

          BOOL -> (boolean)

            

            A Boolean data type.

            

            

          

        

      

    AttributesToGet -> (list)

      

      One or more attributes to retrieve from the table or index. If no attribute names are specified then all attributes will be returned. If any of the specified attributes are not found, they will not appear in the result.

      

      (string)

        

        

      

    ConsistentRead -> (boolean)

      

      The consistency of a read operation. If set to ``true`` , then a strongly consistent read is used; otherwise, an eventually consistent read is used.

      

      

    ProjectionExpression -> (string)

      

      A string that identifies one or more attributes to retrieve from the table. These attributes can include scalars, sets, or elements of a JSON document. The attributes in the *ProjectionExpression* must be separated by commas.

       

      If no attribute names are specified, then all attributes will be returned. If any of the requested attributes are not found, they will not appear in the result.

       

      For more information, see `Accessing Item Attributes`_ in the *Amazon DynamoDB Developer Guide* .

       

      .. note::

        

        *ProjectionExpression* replaces the legacy *AttributesToGet* parameter.

        

      

      

    ExpressionAttributeNames -> (map)

      

      One or more substitution tokens for attribute names in an expression. The following are some use cases for using *ExpressionAttributeNames* :

       

       
      * To access an attribute whose name conflicts with a DynamoDB reserved word. 
       
      * To create a placeholder for repeating occurrences of an attribute name in an expression. 
       
      * To prevent special characters in an attribute name from being misinterpreted in an expression. 
       

       

      Use the **#** character in an expression to dereference an attribute name. For example, consider the following attribute name:

       

      
      * ``Percentile`` 
      

       

      The name of this attribute conflicts with a reserved word, so it cannot be used directly in an expression. (For the complete list of reserved words, see `Reserved Words`_ in the *Amazon DynamoDB Developer Guide* ). To work around this, you could specify the following for *ExpressionAttributeNames* :

       

      
      * ``{"#P":"Percentile"}`` 
      

       

      You could then use this substitution in an expression, as in this example:

       

      
      * ``#P = :val`` 
      

       

      .. note::

        

        Tokens that begin with the **:** character are *expression attribute values* , which are placeholders for the actual value at runtime.

        

       

      For more information on expression attribute names, see `Accessing Item Attributes`_ in the *Amazon DynamoDB Developer Guide* .

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    

  

ConsumedCapacity -> (list)

  

  The read capacity units consumed by the operation.

   

  Each element consists of:

   

   
  * *TableName* - The table that consumed the provisioned throughput. 
   
  * *CapacityUnits* - The total number of capacity units consumed. 
   

  

  (structure)

    

    The capacity units consumed by an operation. The data returned includes the total provisioned throughput consumed, along with statistics for the table and any indexes involved in the operation. *ConsumedCapacity* is only returned if the request asked for it. For more information, see `Provisioned Throughput`_ in the *Amazon DynamoDB Developer Guide* .

    

    TableName -> (string)

      

      The name of the table that was affected by the operation.

      

      

    CapacityUnits -> (double)

      

      The total number of capacity units consumed by the operation.

      

      

    Table -> (structure)

      

      The amount of throughput consumed on the table affected by the operation.

      

      CapacityUnits -> (double)

        

        The total number of capacity units consumed on a table or an index.

        

        

      

    LocalSecondaryIndexes -> (map)

      

      The amount of throughput consumed on each local index affected by the operation.

      

      key -> (string)

        

        

      value -> (structure)

        

        Represents the amount of provisioned throughput capacity consumed on a table or an index. 

        

        CapacityUnits -> (double)

          

          The total number of capacity units consumed on a table or an index.

          

          

        

      

    GlobalSecondaryIndexes -> (map)

      

      The amount of throughput consumed on each global index affected by the operation.

      

      key -> (string)

        

        

      value -> (structure)

        

        Represents the amount of provisioned throughput capacity consumed on a table or an index. 

        

        CapacityUnits -> (double)

          

          The total number of capacity units consumed on a table or an index.

          

          

        

      

    

  



.. _Reserved Words: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ReservedWords.html
.. _Capacity Units Calculations: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/WorkingWithTables.html#CapacityUnitCalculations
.. _Accessing Item Attributes: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Expressions.AccessingItemAttributes.html
.. _Batch Operations and Error Handling: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ErrorHandling.html#BatchOperations
.. _Provisioned Throughput: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ProvisionedThroughputIntro.html
