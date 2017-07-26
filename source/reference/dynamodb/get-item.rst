[ :ref:`aws <cli:aws>` . :ref:`dynamodb <cli:aws dynamodb>` ]

.. _cli:aws dynamodb get-item:


********
get-item
********



===========
Description
===========



The *get-item* operation returns a set of attributes for the item with the given primary key. If there is no matching item, *get-item* does not return any data.

 

*get-item* provides an eventually consistent read by default. If your application requires a strongly consistent read, set *no-consistent-read* to ``true`` . Although a strongly consistent read might take more time than an eventually consistent read, it always returns the last updated value.



========
Synopsis
========

::

    get-item
  --table-name <value>
  --key <value>
  [--attributes-to-get <value>]
  [--consistent-read | --no-consistent-read]
  [--return-consumed-capacity <value>]
  [--projection-expression <value>]
  [--expression-attribute-names <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--table-name`` (string)


  The name of the table containing the requested item.

  

``--key`` (map)


  A map of attribute names to *AttributeValue* objects, representing the primary key of the item to retrieve.

   

  For the primary key, you must provide all of the attributes. For example, with a hash type primary key, you only need to provide the hash attribute. For a hash-and-range type primary key, you must provide both the hash attribute and the range attribute.

  



JSON Syntax::

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



``--attributes-to-get`` (list)


  .. warning::

    

    This is a legacy parameter, for backward compatibility. New applications should use *projection-expression* instead. Do not combine legacy parameters and expression parameters in a single API call; otherwise, DynamoDB will return a *ValidationException* exception.

     

    This parameter allows you to retrieve attributes of type List or Map; however, it cannot retrieve individual elements within a List or a Map.

    

   

  The names of one or more attributes to retrieve. If no attribute names are provided, then all attributes will be returned. If any of the requested attributes are not found, they will not appear in the result.

   

  Note that *AttributesToGet* has no effect on provisioned throughput consumption. DynamoDB determines capacity units consumed based on item size, not on the amount of data that is returned to an application.

  



Syntax::

  "string" "string" ...



``--consistent-read`` | ``--no-consistent-read`` (boolean)


  Determines the read consistency model: If set to ``true`` , then the operation uses strongly consistent reads; otherwise, the operation uses eventually consistent reads.

  

``--return-consumed-capacity`` (string)


  Determines the level of detail about provisioned throughput consumption that is returned in the response:

   

   
  * *INDEXES* - The response includes the aggregate *ConsumedCapacity* for the operation, together with *ConsumedCapacity* for each table and secondary index that was accessed. Note that some operations, such as *get-item* and *batch-get-item* , do not access any indexes at all. In these cases, specifying *INDEXES* will only return *ConsumedCapacity* information for table(s). 
   
  * *TOTAL* - The response includes only the aggregate *ConsumedCapacity* for the operation.
   
  * *NONE* - No *ConsumedCapacity* details are included in the response.
   

  

  Possible values:

  
  *   ``INDEXES``

  
  *   ``TOTAL``

  
  *   ``NONE``

  

  

``--projection-expression`` (string)


  A string that identifies one or more attributes to retrieve from the table. These attributes can include scalars, sets, or elements of a JSON document. The attributes in the expression must be separated by commas.

   

  If no attribute names are specified, then all attributes will be returned. If any of the requested attributes are not found, they will not appear in the result.

   

  For more information, see `Accessing Item Attributes`_ in the *Amazon DynamoDB Developer Guide* .

   

  .. note::

    

    *projection-expression* replaces the legacy *AttributesToGet* parameter.

    

  

``--expression-attribute-names`` (map)


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

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To read an item in a table**

This example retrieves an item from the *MusicCollection* table. The table has a hash-and-range primary key (*Artist* and *SongTitle*), so you must specify both of these ttributes.


Command::

  aws dynamodb get-item --table-name MusicCollection --key file://key.json

The arguments for ``--key`` are stored in a JSON file, ``key.json``.  Here are the contents of that file::

  {
      "Artist": {"S": "Acme Band"},
      "SongTitle": {"S": "Happy Day"}
  }


Output::

  {
      "Item": {
          "AlbumTitle": {
              "S": "Songs About Life"
          }, 
          "SongTitle": {
              "S": "Happy Day"
          }, 
          "Artist": {
              "S": "Acme Band"
          }
      }
  }


======
Output
======

Item -> (map)

  

  A map of attribute names to *AttributeValue* objects, as specified by *AttributesToGet* .

  

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

      

      

    

  

ConsumedCapacity -> (structure)

  

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
.. _Accessing Item Attributes: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Expressions.AccessingItemAttributes.html
.. _Provisioned Throughput: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ProvisionedThroughputIntro.html
