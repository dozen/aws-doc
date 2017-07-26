[ :ref:`aws <cli:aws>` . :ref:`dynamodb <cli:aws dynamodb>` ]

.. _cli:aws dynamodb batch-write-item:


****************
batch-write-item
****************



===========
Description
===========



The ``batch-write-item`` operation puts or deletes multiple items in one or more tables. A single call to ``batch-write-item`` can write up to 16 MB of data, which can comprise as many as 25 put or delete requests. Individual items to be written can be as large as 400 KB.

 

.. note::

   

   ``batch-write-item`` cannot update items. To update items, use the ``update-item`` action.

   

 

The individual ``put-item`` and ``delete-item`` operations specified in ``batch-write-item`` are atomic; however ``batch-write-item`` as a whole is not. If any requested operations fail because the table's provisioned throughput is exceeded or an internal processing failure occurs, the failed operations are returned in the ``UnprocessedItems`` response parameter. You can investigate and optionally resend the requests. Typically, you would call ``batch-write-item`` in a loop. Each iteration would check for unprocessed items and submit a new ``batch-write-item`` request with those unprocessed items until all items have been processed.

 

Note that if *none* of the items can be processed due to insufficient provisioned throughput on all of the tables in the request, then ``batch-write-item`` will return a ``ProvisionedThroughputExceededException`` .

 

.. warning::

   

  If DynamoDB returns any unprocessed items, you should retry the batch operation on those items. However, *we strongly recommend that you use an exponential backoff algorithm* . If you retry the batch operation immediately, the underlying read or write requests can still fail due to throttling on the individual tables. If you delay the batch operation using exponential backoff, the individual requests in the batch are much more likely to succeed.

   

  For more information, see `Batch Operations and Error Handling <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ErrorHandling.html#BatchOperations>`_ in the *Amazon DynamoDB Developer Guide* .

   

 

With ``batch-write-item`` , you can efficiently write or delete large amounts of data, such as from Amazon Elastic MapReduce (EMR), or copy data from another database into DynamoDB. In order to improve performance with these large-scale operations, ``batch-write-item`` does not behave in the same way as individual ``put-item`` and ``delete-item`` calls would. For example, you cannot specify conditions on individual put and delete requests, and ``batch-write-item`` does not return deleted items in the response.

 

If you use a programming language that supports concurrency, you can use threads to write items in parallel. Your application must include the necessary logic to manage the threads. With languages that don't support threading, you must update or delete the specified items one at a time. In both situations, ``batch-write-item`` performs the specified put and delete operations in parallel, giving you the power of the thread pool approach without having to introduce complexity into your application.

 

Parallel processing reduces latency, but each specified put and delete request consumes the same number of write capacity units whether it is processed in parallel or not. Delete operations on nonexistent items consume one write capacity unit.

 

If one or more of the following is true, DynamoDB rejects the entire batch write operation:

 

 
* One or more tables specified in the ``batch-write-item`` request does not exist. 
 
* Primary key attributes specified on an item in the request do not match those in the corresponding table's primary key schema. 
 
* You try to perform multiple operations on the same item in the same ``batch-write-item`` request. For example, you cannot put and delete the same item in the same ``batch-write-item`` request.  
 
* There are more than 25 requests in the batch. 
 
* Any individual item in a batch exceeds 400 KB. 
 
* The total request size exceeds 16 MB. 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dynamodb-2012-08-10/BatchWriteItem>`_


========
Synopsis
========

::

    batch-write-item
  --request-items <value>
  [--return-consumed-capacity <value>]
  [--return-item-collection-metrics <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--request-items`` (map)


  A map of one or more table names and, for each table, a list of operations to be performed (``DeleteRequest`` or ``PutRequest`` ). Each element in the map consists of the following:

   

   
  * ``DeleteRequest`` - Perform a ``delete-item`` operation on the specified item. The item to be deleted is identified by a ``Key`` subelement: 

     
    * ``Key`` - A map of primary key attribute values that uniquely identify the ! item. Each entry in this map consists of an attribute name and an attribute value. For each primary key, you must provide *all* of the key attributes. For example, with a simple primary key, you only need to provide a value for the partition key. For a composite primary key, you must provide values for *both* the partition key and the sort key. 
     

   
   
  * ``PutRequest`` - Perform a ``put-item`` operation on the specified item. The item to be put is identified by an ``Item`` subelement: 

     
    * ``Item`` - A map of attributes and their values. Each entry in this map consists of an attribute name and an attribute value. Attribute values must not be null; string and binary type attributes must have lengths greater than zero; and set type attributes must not be empty. Requests that contain empty values will be rejected with a ``ValidationException`` exception. If you specify any attributes that are part of an index key, then the data types for those attributes must match those of the schema in the table's attribute definition. 
     

   
   

  



JSON Syntax::

  {"string": [
        {
          "PutRequest": {
            "Item": {"string": {
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
          },
          "DeleteRequest": {
            "Key": {"string": {
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
          }
        }
        ...
      ]
    ...}



``--return-consumed-capacity`` (string)


  Determines the level of detail about provisioned throughput consumption that is returned in the response:

   

   
  * ``INDEXES`` - The response includes the aggregate ``ConsumedCapacity`` for the operation, together with ``ConsumedCapacity`` for each table and secondary index that was accessed. Note that some operations, such as ``get-item`` and ``batch-get-item`` , do not access any indexes at all. In these cases, specifying ``INDEXES`` will only return ``ConsumedCapacity`` information for table(s). 
   
  * ``TOTAL`` - The response includes only the aggregate ``ConsumedCapacity`` for the operation. 
   
  * ``NONE`` - No ``ConsumedCapacity`` details are included in the response. 
   

  

  Possible values:

  
  *   ``INDEXES``

  
  *   ``TOTAL``

  
  *   ``NONE``

  

  

``--return-item-collection-metrics`` (string)


  Determines whether item collection metrics are returned. If set to ``SIZE`` , the response includes statistics about item collections, if any, that were modified during the operation are returned in the response. If set to ``NONE`` (the default), no statistics are returned.

  

  Possible values:

  
  *   ``SIZE``

  
  *   ``NONE``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To add multiple items to a table**

This example adds three new items to the *MusicCollection* table using a batch of three PutItem requests.

Command::

  aws dynamodb batch-write-item --request-items file://request-items.json

The arguments for ``--request-items`` are stored in a JSON file, ``request-items.json``.  Here are the contents of that file::

  {
      "MusicCollection": [
          { 
              "PutRequest": {
                  "Item": {
                      "Artist": {"S": "No One You Know"},
                      "SongTitle": {"S": "Call Me Today"},
                      "AlbumTitle": {"S": "Somewhat Famous"}
                  }
              }
          },
          {
              "PutRequest": {
                  "Item": {
                      "Artist": {"S": "Acme Band"},
                      "SongTitle": {"S": "Happy Day"},
                      "AlbumTitle": {"S": "Songs About Life"}
                  }
              }
          },
          {
              "PutRequest": {
                  "Item": {
                      "Artist": {"S": "No One You Know"},
                      "SongTitle": {"S": "Scared of My Shadow"},
                      "AlbumTitle": {"S": "Blue Sky Blues"}
                  }
              }
          }
      ]
  }

Output::

  {
      "UnprocessedItems": {}
  }


======
Output
======

UnprocessedItems -> (map)

  

  A map of tables and requests against those tables that were not processed. The ``UnprocessedItems`` value is in the same form as ``RequestItems`` , so you can provide this value directly to a subsequent ``batch-get-item`` operation. For more information, see ``RequestItems`` in the Request Parameters section.

   

  Each ``UnprocessedItems`` entry consists of a table name and, for that table, a list of operations to perform (``DeleteRequest`` or ``PutRequest`` ).

   

   
  * ``DeleteRequest`` - Perform a ``delete-item`` operation on the specified item. The item to be deleted is identified by a ``Key`` subelement: 

     
    * ``Key`` - A map of primary key attribute values that uniquely identify the item. Each entry in this map consists of an attribute name and an attribute value. 
     

   
   
  * ``PutRequest`` - Perform a ``put-item`` operation on the specified item. The item to be put is identified by an ``Item`` subelement: 

     
    * ``Item`` - A map of attributes and their values. Each entry in this map consists of an attribute name and an attribute value. Attribute values must not be null; string and binary type attributes must have lengths greater than zero; and set type attributes must not be empty. Requests that contain empty values will be rejected with a ``ValidationException`` exception. If you specify any attributes that are part of an index key, then the data types for those attributes must match those of the schema in the table's attribute definition. 
     

   
   

   

  If there are no unprocessed items remaining, the response contains an empty ``UnprocessedItems`` map.

  

  key -> (string)

    

    

  value -> (list)

    

    (structure)

      

      Represents an operation to perform - either ``delete-item`` or ``put-item`` . You can only request one of these operations, not both, in a single ``WriteRequest`` . If you do need to perform both of these operations, you will need to provide two separate ``WriteRequest`` objects.

      

      PutRequest -> (structure)

        

        A request to perform a ``put-item`` operation.

        

        Item -> (map)

          

          A map of attribute name to attribute values, representing the primary key of an item to be processed by ``put-item`` . All of the table's primary key attributes must be specified, and their data types must match those of the table's key schema. If any attributes are present in the item which are part of an index key schema for the table, their types must match the index key schema.

          

          key -> (string)

            

            

          value -> (structure)

            

            Represents the data for an attribute.

             

            Each attribute value is described as a name-value pair. The name is the data type, and the value is the data itself.

             

            For more information, see `Data Types <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.NamingRulesDataTypes.html#HowItWorks.DataTypes>`_ in the *Amazon DynamoDB Developer Guide* .

            

            S -> (string)

              

              An attribute of type String. For example:

               

               ``"S": "Hello"``  

              

              

            N -> (string)

              

              An attribute of type Number. For example:

               

               ``"N": "123.45"``  

               

              Numbers are sent across the network to DynamoDB as strings, to maximize compatibility across languages and libraries. However, DynamoDB treats them as number type attributes for mathematical operations.

              

              

            B -> (blob)

              

              An attribute of type Binary. For example:

               

               ``"B": "dGhpcyB0ZXh0IGlzIGJhc2U2NC1lbmNvZGVk"``  

              

              

            SS -> (list)

              

              An attribute of type String Set. For example:

               

               ``"SS": ["Giraffe", "Hippo" ,"Zebra"]``  

              

              (string)

                

                

              

            NS -> (list)

              

              An attribute of type Number Set. For example:

               

               ``"NS": ["42.2", "-19", "7.5", "3.14"]``  

               

              Numbers are sent across the network to DynamoDB as strings, to maximize compatibility across languages and libraries. However, DynamoDB treats them as number type attributes for mathematical operations.

              

              (string)

                

                

              

            BS -> (list)

              

              An attribute of type Binary Set. For example:

               

               ``"BS": ["U3Vubnk=", "UmFpbnk=", "U25vd3k="]``  

              

              (blob)

                

                

              

            M -> (map)

              

              An attribute of type Map. For example:

               

               ``"M": {"Name": {"S": "Joe"}, "Age": {"N": "35"}}``  

              

              key -> (string)

                

                

              value -> (structure)

                

                Represents the data for an attribute.

                 

                Each attribute value is described as a name-value pair. The name is the data type, and the value is the data itself.

                 

                For more information, see `Data Types <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.NamingRulesDataTypes.html#HowItWorks.DataTypes>`_ in the *Amazon DynamoDB Developer Guide* .

                

                S -> (string)

                  

                  An attribute of type String. For example:

                   

                   ``"S": "Hello"``  

                  

                  

                N -> (string)

                  

                  An attribute of type Number. For example:

                   

                   ``"N": "123.45"``  

                   

                  Numbers are sent across the network to DynamoDB as strings, to maximize compatibility across languages and libraries. However, DynamoDB treats them as number type attributes for mathematical operations.

                  

                  

                B -> (blob)

                  

                  An attribute of type Binary. For example:

                   

                   ``"B": "dGhpcyB0ZXh0IGlzIGJhc2U2NC1lbmNvZGVk"``  

                  

                  

                SS -> (list)

                  

                  An attribute of type String Set. For example:

                   

                   ``"SS": ["Giraffe", "Hippo" ,"Zebra"]``  

                  

                  (string)

                    

                    

                  

                NS -> (list)

                  

                  An attribute of type Number Set. For example:

                   

                   ``"NS": ["42.2", "-19", "7.5", "3.14"]``  

                   

                  Numbers are sent across the network to DynamoDB as strings, to maximize compatibility across languages and libraries. However, DynamoDB treats them as number type attributes for mathematical operations.

                  

                  (string)

                    

                    

                  

                BS -> (list)

                  

                  An attribute of type Binary Set. For example:

                   

                   ``"BS": ["U3Vubnk=", "UmFpbnk=", "U25vd3k="]``  

                  

                  (blob)

                    

                    

                  

                M -> (map)

                  

                  An attribute of type Map. For example:

                   

                   ``"M": {"Name": {"S": "Joe"}, "Age": {"N": "35"}}``  

                  

                  key -> (string)

                    

                    

                  ( ... recursive ... )

                L -> (list)

                  

                  An attribute of type List. For example:

                   

                   ``"L": ["Cookies", "Coffee", 3.14159]``  

                  

                  ( ... recursive ... )

                NULL -> (boolean)

                  

                  An attribute of type Null. For example:

                   

                   ``"NULL": true``  

                  

                  

                BOOL -> (boolean)

                  

                  An attribute of type Boolean. For example:

                   

                   ``"BOOL": true``  

                  

                  

                

              

            L -> (list)

              

              An attribute of type List. For example:

               

               ``"L": ["Cookies", "Coffee", 3.14159]``  

              

              (structure)

                

                Represents the data for an attribute.

                 

                Each attribute value is described as a name-value pair. The name is the data type, and the value is the data itself.

                 

                For more information, see `Data Types <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.NamingRulesDataTypes.html#HowItWorks.DataTypes>`_ in the *Amazon DynamoDB Developer Guide* .

                

                S -> (string)

                  

                  An attribute of type String. For example:

                   

                   ``"S": "Hello"``  

                  

                  

                N -> (string)

                  

                  An attribute of type Number. For example:

                   

                   ``"N": "123.45"``  

                   

                  Numbers are sent across the network to DynamoDB as strings, to maximize compatibility across languages and libraries. However, DynamoDB treats them as number type attributes for mathematical operations.

                  

                  

                B -> (blob)

                  

                  An attribute of type Binary. For example:

                   

                   ``"B": "dGhpcyB0ZXh0IGlzIGJhc2U2NC1lbmNvZGVk"``  

                  

                  

                SS -> (list)

                  

                  An attribute of type String Set. For example:

                   

                   ``"SS": ["Giraffe", "Hippo" ,"Zebra"]``  

                  

                  (string)

                    

                    

                  

                NS -> (list)

                  

                  An attribute of type Number Set. For example:

                   

                   ``"NS": ["42.2", "-19", "7.5", "3.14"]``  

                   

                  Numbers are sent across the network to DynamoDB as strings, to maximize compatibility across languages and libraries. However, DynamoDB treats them as number type attributes for mathematical operations.

                  

                  (string)

                    

                    

                  

                BS -> (list)

                  

                  An attribute of type Binary Set. For example:

                   

                   ``"BS": ["U3Vubnk=", "UmFpbnk=", "U25vd3k="]``  

                  

                  (blob)

                    

                    

                  

                M -> (map)

                  

                  An attribute of type Map. For example:

                   

                   ``"M": {"Name": {"S": "Joe"}, "Age": {"N": "35"}}``  

                  

                  key -> (string)

                    

                    

                  ( ... recursive ... )

                L -> (list)

                  

                  An attribute of type List. For example:

                   

                   ``"L": ["Cookies", "Coffee", 3.14159]``  

                  

                  ( ... recursive ... )

                NULL -> (boolean)

                  

                  An attribute of type Null. For example:

                   

                   ``"NULL": true``  

                  

                  

                BOOL -> (boolean)

                  

                  An attribute of type Boolean. For example:

                   

                   ``"BOOL": true``  

                  

                  

                

              

            NULL -> (boolean)

              

              An attribute of type Null. For example:

               

               ``"NULL": true``  

              

              

            BOOL -> (boolean)

              

              An attribute of type Boolean. For example:

               

               ``"BOOL": true``  

              

              

            

          

        

      DeleteRequest -> (structure)

        

        A request to perform a ``delete-item`` operation.

        

        Key -> (map)

          

          A map of attribute name to attribute values, representing the primary key of the item to delete. All of the table's primary key attributes must be specified, and their data types must match those of the table's key schema.

          

          key -> (string)

            

            

          value -> (structure)

            

            Represents the data for an attribute.

             

            Each attribute value is described as a name-value pair. The name is the data type, and the value is the data itself.

             

            For more information, see `Data Types <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.NamingRulesDataTypes.html#HowItWorks.DataTypes>`_ in the *Amazon DynamoDB Developer Guide* .

            

            S -> (string)

              

              An attribute of type String. For example:

               

               ``"S": "Hello"``  

              

              

            N -> (string)

              

              An attribute of type Number. For example:

               

               ``"N": "123.45"``  

               

              Numbers are sent across the network to DynamoDB as strings, to maximize compatibility across languages and libraries. However, DynamoDB treats them as number type attributes for mathematical operations.

              

              

            B -> (blob)

              

              An attribute of type Binary. For example:

               

               ``"B": "dGhpcyB0ZXh0IGlzIGJhc2U2NC1lbmNvZGVk"``  

              

              

            SS -> (list)

              

              An attribute of type String Set. For example:

               

               ``"SS": ["Giraffe", "Hippo" ,"Zebra"]``  

              

              (string)

                

                

              

            NS -> (list)

              

              An attribute of type Number Set. For example:

               

               ``"NS": ["42.2", "-19", "7.5", "3.14"]``  

               

              Numbers are sent across the network to DynamoDB as strings, to maximize compatibility across languages and libraries. However, DynamoDB treats them as number type attributes for mathematical operations.

              

              (string)

                

                

              

            BS -> (list)

              

              An attribute of type Binary Set. For example:

               

               ``"BS": ["U3Vubnk=", "UmFpbnk=", "U25vd3k="]``  

              

              (blob)

                

                

              

            M -> (map)

              

              An attribute of type Map. For example:

               

               ``"M": {"Name": {"S": "Joe"}, "Age": {"N": "35"}}``  

              

              key -> (string)

                

                

              value -> (structure)

                

                Represents the data for an attribute.

                 

                Each attribute value is described as a name-value pair. The name is the data type, and the value is the data itself.

                 

                For more information, see `Data Types <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.NamingRulesDataTypes.html#HowItWorks.DataTypes>`_ in the *Amazon DynamoDB Developer Guide* .

                

                S -> (string)

                  

                  An attribute of type String. For example:

                   

                   ``"S": "Hello"``  

                  

                  

                N -> (string)

                  

                  An attribute of type Number. For example:

                   

                   ``"N": "123.45"``  

                   

                  Numbers are sent across the network to DynamoDB as strings, to maximize compatibility across languages and libraries. However, DynamoDB treats them as number type attributes for mathematical operations.

                  

                  

                B -> (blob)

                  

                  An attribute of type Binary. For example:

                   

                   ``"B": "dGhpcyB0ZXh0IGlzIGJhc2U2NC1lbmNvZGVk"``  

                  

                  

                SS -> (list)

                  

                  An attribute of type String Set. For example:

                   

                   ``"SS": ["Giraffe", "Hippo" ,"Zebra"]``  

                  

                  (string)

                    

                    

                  

                NS -> (list)

                  

                  An attribute of type Number Set. For example:

                   

                   ``"NS": ["42.2", "-19", "7.5", "3.14"]``  

                   

                  Numbers are sent across the network to DynamoDB as strings, to maximize compatibility across languages and libraries. However, DynamoDB treats them as number type attributes for mathematical operations.

                  

                  (string)

                    

                    

                  

                BS -> (list)

                  

                  An attribute of type Binary Set. For example:

                   

                   ``"BS": ["U3Vubnk=", "UmFpbnk=", "U25vd3k="]``  

                  

                  (blob)

                    

                    

                  

                M -> (map)

                  

                  An attribute of type Map. For example:

                   

                   ``"M": {"Name": {"S": "Joe"}, "Age": {"N": "35"}}``  

                  

                  key -> (string)

                    

                    

                  ( ... recursive ... )

                L -> (list)

                  

                  An attribute of type List. For example:

                   

                   ``"L": ["Cookies", "Coffee", 3.14159]``  

                  

                  ( ... recursive ... )

                NULL -> (boolean)

                  

                  An attribute of type Null. For example:

                   

                   ``"NULL": true``  

                  

                  

                BOOL -> (boolean)

                  

                  An attribute of type Boolean. For example:

                   

                   ``"BOOL": true``  

                  

                  

                

              

            L -> (list)

              

              An attribute of type List. For example:

               

               ``"L": ["Cookies", "Coffee", 3.14159]``  

              

              (structure)

                

                Represents the data for an attribute.

                 

                Each attribute value is described as a name-value pair. The name is the data type, and the value is the data itself.

                 

                For more information, see `Data Types <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.NamingRulesDataTypes.html#HowItWorks.DataTypes>`_ in the *Amazon DynamoDB Developer Guide* .

                

                S -> (string)

                  

                  An attribute of type String. For example:

                   

                   ``"S": "Hello"``  

                  

                  

                N -> (string)

                  

                  An attribute of type Number. For example:

                   

                   ``"N": "123.45"``  

                   

                  Numbers are sent across the network to DynamoDB as strings, to maximize compatibility across languages and libraries. However, DynamoDB treats them as number type attributes for mathematical operations.

                  

                  

                B -> (blob)

                  

                  An attribute of type Binary. For example:

                   

                   ``"B": "dGhpcyB0ZXh0IGlzIGJhc2U2NC1lbmNvZGVk"``  

                  

                  

                SS -> (list)

                  

                  An attribute of type String Set. For example:

                   

                   ``"SS": ["Giraffe", "Hippo" ,"Zebra"]``  

                  

                  (string)

                    

                    

                  

                NS -> (list)

                  

                  An attribute of type Number Set. For example:

                   

                   ``"NS": ["42.2", "-19", "7.5", "3.14"]``  

                   

                  Numbers are sent across the network to DynamoDB as strings, to maximize compatibility across languages and libraries. However, DynamoDB treats them as number type attributes for mathematical operations.

                  

                  (string)

                    

                    

                  

                BS -> (list)

                  

                  An attribute of type Binary Set. For example:

                   

                   ``"BS": ["U3Vubnk=", "UmFpbnk=", "U25vd3k="]``  

                  

                  (blob)

                    

                    

                  

                M -> (map)

                  

                  An attribute of type Map. For example:

                   

                   ``"M": {"Name": {"S": "Joe"}, "Age": {"N": "35"}}``  

                  

                  key -> (string)

                    

                    

                  ( ... recursive ... )

                L -> (list)

                  

                  An attribute of type List. For example:

                   

                   ``"L": ["Cookies", "Coffee", 3.14159]``  

                  

                  ( ... recursive ... )

                NULL -> (boolean)

                  

                  An attribute of type Null. For example:

                   

                   ``"NULL": true``  

                  

                  

                BOOL -> (boolean)

                  

                  An attribute of type Boolean. For example:

                   

                   ``"BOOL": true``  

                  

                  

                

              

            NULL -> (boolean)

              

              An attribute of type Null. For example:

               

               ``"NULL": true``  

              

              

            BOOL -> (boolean)

              

              An attribute of type Boolean. For example:

               

               ``"BOOL": true``  

              

              

            

          

        

      

    

  

ItemCollectionMetrics -> (map)

  

  A list of tables that were processed by ``batch-write-item`` and, for each table, information about any item collections that were affected by individual ``delete-item`` or ``put-item`` operations.

   

  Each entry consists of the following subelements:

   

   
  * ``ItemCollectionKey`` - The partition key value of the item collection. This is the same as the partition key value of the item. 
   
  * ``SizeEstimateRange`` - An estimate of item collection size, expressed in GB. This is a two-element array containing a lower bound and an upper bound for the estimate. The estimate includes the size of all the items in the table, plus the size of all attributes projected into all of the local secondary indexes on the table. Use this estimate to measure whether a local secondary index is approaching its size limit. The estimate is subject to change over time; therefore, do not rely on the precision or accuracy of the estimate. 
   

  

  key -> (string)

    

    

  value -> (list)

    

    (structure)

      

      Information about item collections, if any, that were affected by the operation. ``ItemCollectionMetrics`` is only returned if the request asked for it. If the table does not have any local secondary indexes, this information is not returned in the response.

      

      ItemCollectionKey -> (map)

        

        The partition key value of the item collection. This value is the same as the partition key value of the item.

        

        key -> (string)

          

          

        value -> (structure)

          

          Represents the data for an attribute.

           

          Each attribute value is described as a name-value pair. The name is the data type, and the value is the data itself.

           

          For more information, see `Data Types <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.NamingRulesDataTypes.html#HowItWorks.DataTypes>`_ in the *Amazon DynamoDB Developer Guide* .

          

          S -> (string)

            

            An attribute of type String. For example:

             

             ``"S": "Hello"``  

            

            

          N -> (string)

            

            An attribute of type Number. For example:

             

             ``"N": "123.45"``  

             

            Numbers are sent across the network to DynamoDB as strings, to maximize compatibility across languages and libraries. However, DynamoDB treats them as number type attributes for mathematical operations.

            

            

          B -> (blob)

            

            An attribute of type Binary. For example:

             

             ``"B": "dGhpcyB0ZXh0IGlzIGJhc2U2NC1lbmNvZGVk"``  

            

            

          SS -> (list)

            

            An attribute of type String Set. For example:

             

             ``"SS": ["Giraffe", "Hippo" ,"Zebra"]``  

            

            (string)

              

              

            

          NS -> (list)

            

            An attribute of type Number Set. For example:

             

             ``"NS": ["42.2", "-19", "7.5", "3.14"]``  

             

            Numbers are sent across the network to DynamoDB as strings, to maximize compatibility across languages and libraries. However, DynamoDB treats them as number type attributes for mathematical operations.

            

            (string)

              

              

            

          BS -> (list)

            

            An attribute of type Binary Set. For example:

             

             ``"BS": ["U3Vubnk=", "UmFpbnk=", "U25vd3k="]``  

            

            (blob)

              

              

            

          M -> (map)

            

            An attribute of type Map. For example:

             

             ``"M": {"Name": {"S": "Joe"}, "Age": {"N": "35"}}``  

            

            key -> (string)

              

              

            value -> (structure)

              

              Represents the data for an attribute.

               

              Each attribute value is described as a name-value pair. The name is the data type, and the value is the data itself.

               

              For more information, see `Data Types <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.NamingRulesDataTypes.html#HowItWorks.DataTypes>`_ in the *Amazon DynamoDB Developer Guide* .

              

              S -> (string)

                

                An attribute of type String. For example:

                 

                 ``"S": "Hello"``  

                

                

              N -> (string)

                

                An attribute of type Number. For example:

                 

                 ``"N": "123.45"``  

                 

                Numbers are sent across the network to DynamoDB as strings, to maximize compatibility across languages and libraries. However, DynamoDB treats them as number type attributes for mathematical operations.

                

                

              B -> (blob)

                

                An attribute of type Binary. For example:

                 

                 ``"B": "dGhpcyB0ZXh0IGlzIGJhc2U2NC1lbmNvZGVk"``  

                

                

              SS -> (list)

                

                An attribute of type String Set. For example:

                 

                 ``"SS": ["Giraffe", "Hippo" ,"Zebra"]``  

                

                (string)

                  

                  

                

              NS -> (list)

                

                An attribute of type Number Set. For example:

                 

                 ``"NS": ["42.2", "-19", "7.5", "3.14"]``  

                 

                Numbers are sent across the network to DynamoDB as strings, to maximize compatibility across languages and libraries. However, DynamoDB treats them as number type attributes for mathematical operations.

                

                (string)

                  

                  

                

              BS -> (list)

                

                An attribute of type Binary Set. For example:

                 

                 ``"BS": ["U3Vubnk=", "UmFpbnk=", "U25vd3k="]``  

                

                (blob)

                  

                  

                

              M -> (map)

                

                An attribute of type Map. For example:

                 

                 ``"M": {"Name": {"S": "Joe"}, "Age": {"N": "35"}}``  

                

                key -> (string)

                  

                  

                ( ... recursive ... )

              L -> (list)

                

                An attribute of type List. For example:

                 

                 ``"L": ["Cookies", "Coffee", 3.14159]``  

                

                ( ... recursive ... )

              NULL -> (boolean)

                

                An attribute of type Null. For example:

                 

                 ``"NULL": true``  

                

                

              BOOL -> (boolean)

                

                An attribute of type Boolean. For example:

                 

                 ``"BOOL": true``  

                

                

              

            

          L -> (list)

            

            An attribute of type List. For example:

             

             ``"L": ["Cookies", "Coffee", 3.14159]``  

            

            (structure)

              

              Represents the data for an attribute.

               

              Each attribute value is described as a name-value pair. The name is the data type, and the value is the data itself.

               

              For more information, see `Data Types <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.NamingRulesDataTypes.html#HowItWorks.DataTypes>`_ in the *Amazon DynamoDB Developer Guide* .

              

              S -> (string)

                

                An attribute of type String. For example:

                 

                 ``"S": "Hello"``  

                

                

              N -> (string)

                

                An attribute of type Number. For example:

                 

                 ``"N": "123.45"``  

                 

                Numbers are sent across the network to DynamoDB as strings, to maximize compatibility across languages and libraries. However, DynamoDB treats them as number type attributes for mathematical operations.

                

                

              B -> (blob)

                

                An attribute of type Binary. For example:

                 

                 ``"B": "dGhpcyB0ZXh0IGlzIGJhc2U2NC1lbmNvZGVk"``  

                

                

              SS -> (list)

                

                An attribute of type String Set. For example:

                 

                 ``"SS": ["Giraffe", "Hippo" ,"Zebra"]``  

                

                (string)

                  

                  

                

              NS -> (list)

                

                An attribute of type Number Set. For example:

                 

                 ``"NS": ["42.2", "-19", "7.5", "3.14"]``  

                 

                Numbers are sent across the network to DynamoDB as strings, to maximize compatibility across languages and libraries. However, DynamoDB treats them as number type attributes for mathematical operations.

                

                (string)

                  

                  

                

              BS -> (list)

                

                An attribute of type Binary Set. For example:

                 

                 ``"BS": ["U3Vubnk=", "UmFpbnk=", "U25vd3k="]``  

                

                (blob)

                  

                  

                

              M -> (map)

                

                An attribute of type Map. For example:

                 

                 ``"M": {"Name": {"S": "Joe"}, "Age": {"N": "35"}}``  

                

                key -> (string)

                  

                  

                ( ... recursive ... )

              L -> (list)

                

                An attribute of type List. For example:

                 

                 ``"L": ["Cookies", "Coffee", 3.14159]``  

                

                ( ... recursive ... )

              NULL -> (boolean)

                

                An attribute of type Null. For example:

                 

                 ``"NULL": true``  

                

                

              BOOL -> (boolean)

                

                An attribute of type Boolean. For example:

                 

                 ``"BOOL": true``  

                

                

              

            

          NULL -> (boolean)

            

            An attribute of type Null. For example:

             

             ``"NULL": true``  

            

            

          BOOL -> (boolean)

            

            An attribute of type Boolean. For example:

             

             ``"BOOL": true``  

            

            

          

        

      SizeEstimateRangeGB -> (list)

        

        An estimate of item collection size, in gigabytes. This value is a two-element array containing a lower bound and an upper bound for the estimate. The estimate includes the size of all the items in the table, plus the size of all attributes projected into all of the local secondary indexes on that table. Use this estimate to measure whether a local secondary index is approaching its size limit.

         

        The estimate is subject to change over time; therefore, do not rely on the precision or accuracy of the estimate.

        

        (double)

          

          

        

      

    

  

ConsumedCapacity -> (list)

  

  The capacity units consumed by the entire ``batch-write-item`` operation.

   

  Each element consists of:

   

   
  * ``TableName`` - The table that consumed the provisioned throughput. 
   
  * ``CapacityUnits`` - The total number of capacity units consumed. 
   

  

  (structure)

    

    The capacity units consumed by an operation. The data returned includes the total provisioned throughput consumed, along with statistics for the table and any indexes involved in the operation. ``ConsumedCapacity`` is only returned if the request asked for it. For more information, see `Provisioned Throughput <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ProvisionedThroughputIntro.html>`_ in the *Amazon DynamoDB Developer Guide* .

    

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

          

          

        

      

    

  

