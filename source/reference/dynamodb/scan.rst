[ :ref:`aws <cli:aws>` . :ref:`dynamodb <cli:aws dynamodb>` ]

.. _cli:aws dynamodb scan:


****
scan
****



===========
Description
===========



The *scan* operation returns one or more items and item attributes by accessing every item in a table or a secondary index. To have DynamoDB return fewer items, you can provide a *ScanFilter* operation.

 

If the total number of scanned items exceeds the maximum data set size limit of 1 MB, the scan stops and results are returned to the user as a *LastEvaluatedKey* value to continue the scan in a subsequent operation. The results also include the number of items exceeding the limit. A scan can result in no table data meeting the filter criteria. 

 

By default, *scan* operations proceed sequentially; however, for faster performance on a large table or secondary index, applications can request a parallel *scan* operation by providing the *Segment* and *TotalSegments* parameters. For more information, see `Parallel scan`_ in the *Amazon DynamoDB Developer Guide* .

 

By default, *scan* uses eventually consistent reads when acessing the data in the table or local secondary index. However, you can use strongly consistent reads instead by setting the *no-consistent-read* parameter to *true* .



``scan`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Items``, ``Count``, ``ScannedCount``


========
Synopsis
========

::

    scan
  --table-name <value>
  [--index-name <value>]
  [--attributes-to-get <value>]
  [--select <value>]
  [--scan-filter <value>]
  [--conditional-operator <value>]
  [--return-consumed-capacity <value>]
  [--total-segments <value>]
  [--segment <value>]
  [--projection-expression <value>]
  [--filter-expression <value>]
  [--expression-attribute-names <value>]
  [--expression-attribute-values <value>]
  [--consistent-read | --no-consistent-read]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--table-name`` (string)


  The name of the table containing the requested items; or, if you provide ``index-name`` , the name of the table to which that index belongs.

  

``--index-name`` (string)


  The name of a secondary index to scan. This index can be any local secondary index or global secondary index. Note that if you use the ``index-name`` parameter, you must also provide ``table-name`` .

  

``--attributes-to-get`` (list)


  .. warning::

    

    This is a legacy parameter, for backward compatibility. New applications should use *projection-expression* instead. Do not combine legacy parameters and expression parameters in a single API call; otherwise, DynamoDB will return a *ValidationException* exception.

     

    This parameter allows you to retrieve attributes of type List or Map; however, it cannot retrieve individual elements within a List or a Map.

    

   

  The names of one or more attributes to retrieve. If no attribute names are provided, then all attributes will be returned. If any of the requested attributes are not found, they will not appear in the result.

   

  Note that *AttributesToGet* has no effect on provisioned throughput consumption. DynamoDB determines capacity units consumed based on item size, not on the amount of data that is returned to an application.

  



Syntax::

  "string" "string" ...



``--select`` (string)


  The attributes to be returned in the result. You can retrieve all item attributes, specific item attributes, or the count of matching items.

   

   
  * ``ALL_ATTRIBUTES`` - Returns all of the item attributes. 
   
  * ``COUNT`` - Returns the number of matching items, rather than the matching items themselves. 
   
  * ``SPECIFIC_ATTRIBUTES`` - Returns only the attributes listed in *AttributesToGet* . This return value is equivalent to specifying *AttributesToGet* without specifying any value for *select* . 
   

   

  If neither *select* nor *AttributesToGet* are specified, DynamoDB defaults to ``ALL_ATTRIBUTES`` . You cannot use both *AttributesToGet* and *select* together in a single request, unless the value for *select* is ``SPECIFIC_ATTRIBUTES`` . (This usage is equivalent to specifying *AttributesToGet* without any value for *select* .)

  

  Possible values:

  
  *   ``ALL_ATTRIBUTES``

  
  *   ``ALL_PROJECTED_ATTRIBUTES``

  
  *   ``SPECIFIC_ATTRIBUTES``

  
  *   ``COUNT``

  

  

``--scan-filter`` (map)


  .. warning::

     

    This is a legacy parameter, for backward compatibility. New applications should use *FilterExpression* instead. Do not combine legacy parameters and expression parameters in a single API call; otherwise, DynamoDB will return a *ValidationException* exception.

     

   

  A condition that evaluates the scan results and returns only the desired values.

   

  .. note::

    

    This parameter does not support attributes of type List or Map.

    

   

  If you specify more than one condition in the *ScanFilter* map, then by default all of the conditions must evaluate to true. In other words, the conditions are ANDed together. (You can use the *conditional-operator* parameter to OR the conditions instead. If you do this, then at least one of the conditions must evaluate to true, rather than all of them.)

   

  Each *ScanFilter* element consists of an attribute name to compare, along with the following:

   

   
  * *AttributeValueList* - One or more values to evaluate against the supplied attribute. The number of values in the list depends on the operator specified in *ComparisonOperator* . For type Number, value comparisons are numeric. String value comparisons for greater than, equals, or less than are based on ASCII character code values. For example, ``a`` is greater than ``A`` , and ``a`` is greater than ``B`` . For a list of code values, see `http\://en.wikipedia.org/wiki/ASCII#ASCII_printable_characters`_ . For Binary, DynamoDB treats each byte of the binary data as unsigned when it compares binary values. For information on specifying data types in JSON, see `JSON Data Format`_ in the *Amazon DynamoDB Developer Guide* . 
   
  * *ComparisonOperator* - A comparator for evaluating attributes. For example, equals, greater than, less than, etc. The following comparison operators are available: ``EQ | NE | LE | LT | GE | GT | NOT_NULL | NULL | CONTAINS | NOT_CONTAINS | BEGINS_WITH | IN | BETWEEN``  For complete descriptions of all comparison operators, see `Condition`_ . 
   

  



JSON Syntax::

  {"string": {
        "AttributeValueList": [
          {
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
          ...
        ],
        "ComparisonOperator": "EQ"|"NE"|"IN"|"LE"|"LT"|"GE"|"GT"|"BETWEEN"|"NOT_NULL"|"NULL"|"CONTAINS"|"NOT_CONTAINS"|"BEGINS_WITH"
      }
    ...}



``--conditional-operator`` (string)


  .. warning::

     

    This is a legacy parameter, for backward compatibility. New applications should use *FilterExpression* instead. Do not combine legacy parameters and expression parameters in a single API call; otherwise, DynamoDB will return a *ValidationException* exception.

     

   

  A logical operator to apply to the conditions in a *ScanFilter* map:

   

   
  * ``AND`` - If all of the conditions evaluate to true, then the entire map evaluates to true.
   
  * ``OR`` - If at least one of the conditions evaluate to true, then the entire map evaluates to true.
   

   

  If you omit *conditional-operator* , then ``AND`` is the default.

   

  The operation will succeed only if the entire map evaluates to true.

   

  .. note::

    

    This parameter does not support attributes of type List or Map.

    

  

  Possible values:

  
  *   ``AND``

  
  *   ``OR``

  

  

``--return-consumed-capacity`` (string)


  Determines the level of detail about provisioned throughput consumption that is returned in the response:

   

   
  * *INDEXES* - The response includes the aggregate *ConsumedCapacity* for the operation, together with *ConsumedCapacity* for each table and secondary index that was accessed. Note that some operations, such as *get-item* and *batch-get-item* , do not access any indexes at all. In these cases, specifying *INDEXES* will only return *ConsumedCapacity* information for table(s). 
   
  * *TOTAL* - The response includes only the aggregate *ConsumedCapacity* for the operation.
   
  * *NONE* - No *ConsumedCapacity* details are included in the response.
   

  

  Possible values:

  
  *   ``INDEXES``

  
  *   ``TOTAL``

  
  *   ``NONE``

  

  

``--total-segments`` (integer)


  For a parallel *scan* request, *TotalSegments* represents the total number of segments into which the *scan* operation will be divided. The value of *TotalSegments* corresponds to the number of application workers that will perform the parallel scan. For example, if you want to use four application threads to scan a table or an index, specify a *TotalSegments* value of 4.

   

  The value for *TotalSegments* must be greater than or equal to 1, and less than or equal to 1000000. If you specify a *TotalSegments* value of 1, the *scan* operation will be sequential rather than parallel.

   

  If you specify *TotalSegments* , you must also specify *Segment* .

  

``--segment`` (integer)


  For a parallel *scan* request, *Segment* identifies an individual segment to be scanned by an application worker.

   

  Segment IDs are zero-based, so the first segment is always 0. For example, if you want to use four application threads to scan a table or an index, then the first thread specifies a *Segment* value of 0, the second thread specifies 1, and so on.

   

  The value of *LastEvaluatedKey* returned from a parallel *scan* request must be used as *ExclusiveStartKey* with the same segment ID in a subsequent *scan* operation.

   

  The value for *Segment* must be greater than or equal to 0, and less than the value provided for *TotalSegments* .

   

  If you provide *Segment* , you must also provide *TotalSegments* .

  

``--projection-expression`` (string)


  A string that identifies one or more attributes to retrieve from the specified table or index. These attributes can include scalars, sets, or elements of a JSON document. The attributes in the expression must be separated by commas.

   

  If no attribute names are specified, then all attributes will be returned. If any of the requested attributes are not found, they will not appear in the result.

   

  For more information, see `Accessing Item Attributes`_ in the *Amazon DynamoDB Developer Guide* .

   

  .. note::

    

    *projection-expression* replaces the legacy *AttributesToGet* parameter.

    

  

``--filter-expression`` (string)


  A string that contains conditions that DynamoDB applies after the *scan* operation, but before the data is returned to you. Items that do not satisfy the *FilterExpression* criteria are not returned.

   

  .. note::

     

    A *FilterExpression* is applied after the items have already been read; the process of filtering does not consume any additional read capacity units.

    

   

  For more information, see `Filter Expressions`_ in the *Amazon DynamoDB Developer Guide* .

   

  .. note::

    

    *FilterExpression* replaces the legacy *ScanFilter* and *conditional-operator* parameters.

    

  

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



``--expression-attribute-values`` (map)


  One or more values that can be substituted in an expression.

   

  Use the **:** (colon) character in an expression to dereference an attribute value. For example, suppose that you wanted to check whether the value of the *ProductStatus* attribute was one of the following: 

   

  ``Available | Backordered | Discontinued`` 

   

  You would first need to specify *ExpressionAttributeValues* as follows:

   

  ``{ ":avail":{"S":"Available"}, ":back":{"S":"Backordered"}, ":disc":{"S":"Discontinued"} }`` 

   

  You could then use these values in an expression, such as this:

   

  ``ProductStatus IN (:avail, :back, :disc)`` 

   

  For more information on expression attribute values, see `Specifying Conditions`_ in the *Amazon DynamoDB Developer Guide* .

  



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



``--consistent-read`` | ``--no-consistent-read`` (boolean)


  A Boolean value that determines the read consistency model during the scan:

   

   
  * If *no-consistent-read* is ``false`` , then *scan* will use eventually consistent reads. The data returned from *scan* might not contain the results of other recently completed write operations (PutItem, update-item or DeleteItem). The *scan* response might include some stale data. 
   
  * If *no-consistent-read* is ``true`` , then *scan* will use strongly consistent reads. All of the write operations that completed before the *scan* began are guaranteed to be contained in the *scan* response. 
   

   

  The default setting for *no-consistent-read* is ``false`` , meaning that eventually consistent reads will be used.

   

  Strongly consistent reads are not supported on global secondary indexes. If you scan a global secondary index with *no-consistent-read* set to true, you will receive a *ValidationException* .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To scan a table**

This example scans the entire *MusicCollection* table, and then narrows the results to songs by the artist "No One You Know". For each item, only the album title and song title are returned. 

Command::

  aws dynamodb scan --table-name MusicCollection --filter-expression "Artist = :a" --projection-expression "#ST, #AT" --expression-attribute-names file://expression-attribute-names.json --expression-attribute-values file://expression-attribute-values.json 

The arguments for ``--expression-attribute-names`` are stored in a JSON file, ``expression-attribute-names.json``.  Here are the contents of that file::

  {
      "#ST": "SongTitle", 
      "#AT":"AlbumTitle"
  }


The arguments for ``--expression-attribute-values`` are stored in a JSON file, ``expression-attribute-values.json``.  Here are the contents of that file::

  {
      ":a": {"S": "No One You Know"}
  }

Output::

  {
      "Count": 2, 
      "Items": [
          {
              "SongTitle": {
                  "S": "Call Me Today"
              }, 
              "AlbumTitle": {
                  "S": "Somewhat Famous"
              }
          }, 
          {
              "SongTitle": {
                  "S": "Scared of My Shadow"
              }, 
              "AlbumTitle": {
                  "S": "Blue Sky Blues"
              }
          }
      ], 
      "ScannedCount": 3, 
      "ConsumedCapacity": null
  }


======
Output
======

Items -> (list)

  

  An array of item attributes that match the scan criteria. Each element in this array consists of an attribute name and the value for that attribute.

  

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

        

        

      

    

  

Count -> (integer)

  

  The number of items in the response.

   

  If you set *ScanFilter* in the request, then *Count* is the number of items returned after the filter was applied, and *ScannedCount* is the number of matching items before the filter was applied.

   

  If you did not use a filter in the request, then *Count* is the same as *ScannedCount* .

  

  

ScannedCount -> (integer)

  

  The number of items evaluated, before any *ScanFilter* is applied. A high *ScannedCount* value with few, or no, *Count* results indicates an inefficient *scan* operation. For more information, see `Count and ScannedCount`_ in the *Amazon DynamoDB Developer Guide* .

   

  If you did not use a filter in the request, then *ScannedCount* is the same as *Count* .

  

  

LastEvaluatedKey -> (map)

  

  The primary key of the item where the operation stopped, inclusive of the previous result set. Use this value to start a new operation, excluding this value in the new request.

   

  If *LastEvaluatedKey* is empty, then the "last page" of results has been processed and there is no more data to be retrieved.

   

  If *LastEvaluatedKey* is not empty, it does not necessarily mean that there is more data in the result set. The only way to know when you have reached the end of the result set is when *LastEvaluatedKey* is empty.

  

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

        

        

      

    

  



.. _Filter Expressions: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/QueryAndScan.html#FilteringResults
.. _Provisioned Throughput: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ProvisionedThroughputIntro.html
.. _Reserved Words: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ReservedWords.html
.. _JSON Data Format: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DataFormat.html
.. _Parallel scan: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/QueryAndScan.html#QueryAndScanParallelScan
.. _Accessing Item Attributes: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Expressions.AccessingItemAttributes.html
.. _Count and ScannedCount: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/QueryAndScan.html#Count
.. _Specifying Conditions: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Expressions.SpecifyingConditions.html
.. _http\://en.wikipedia.org/wiki/ASCII#ASCII_printable_characters: http://en.wikipedia.org/wiki/ASCII#ASCII_printable_characters
.. _Condition: http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_Condition.html
