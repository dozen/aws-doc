[ :ref:`aws <cli:aws>` . :ref:`dynamodb <cli:aws dynamodb>` ]

.. _cli:aws dynamodb query:


*****
query
*****



===========
Description
===========



A *query* operation uses the primary key of a table or a secondary index to directly access items from that table or index.

 

Use the *KeyConditionExpression* parameter to provide a specific hash key value. The *query* operation will return all of the items from the table or index with that hash key value. You can optionally narrow the scope of the *query* operation by specifying a range key value and a comparison operator in *KeyConditionExpression* . You can use the *ScanIndexForward* parameter to get results in forward or reverse order, by range key or by index key. 

 

Queries that do not return results consume the minimum number of read capacity units for that type of read operation.

 

If the total number of items meeting the query criteria exceeds the result set size limit of 1 MB, the query stops and results are returned to the user with the *LastEvaluatedKey* element to continue the query in a subsequent operation. Unlike a *scan* operation, a *query* operation never returns both an empty result set and a *LastEvaluatedKey* value. *LastEvaluatedKey* is only provided if the results exceed 1 MB, or if you have used the *Limit* parameter. 

 

You can query a table, a local secondary index, or a global secondary index. For a query on a table or on a local secondary index, you can set the *no-consistent-read* parameter to ``true`` and obtain a strongly consistent result. Global secondary indexes support eventually consistent reads only, so do not specify *no-consistent-read* when querying a global secondary index.



``query`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Items``, ``Count``, ``ScannedCount``


========
Synopsis
========

::

    query
  --table-name <value>
  [--index-name <value>]
  [--select <value>]
  [--attributes-to-get <value>]
  [--consistent-read | --no-consistent-read]
  [--key-conditions <value>]
  [--query-filter <value>]
  [--conditional-operator <value>]
  [--scan-index-forward | --no-scan-index-forward]
  [--return-consumed-capacity <value>]
  [--projection-expression <value>]
  [--filter-expression <value>]
  [--key-condition-expression <value>]
  [--expression-attribute-names <value>]
  [--expression-attribute-values <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--table-name`` (string)


  The name of the table containing the requested items. 

  

``--index-name`` (string)


  The name of an index to query. This index can be any local secondary index or global secondary index on the table. Note that if you use the *index-name* parameter, you must also provide *TableName.* 

  

``--select`` (string)


  The attributes to be returned in the result. You can retrieve all item attributes, specific item attributes, the count of matching items, or in the case of an index, some or all of the attributes projected into the index.

   

   
  * ``ALL_ATTRIBUTES`` - Returns all of the item attributes from the specified table or index. If you query a local secondary index, then for each matching item in the index DynamoDB will fetch the entire item from the parent table. If the index is configured to project all item attributes, then all of the data can be obtained from the local secondary index, and no fetching is required. 
   
  * ``ALL_PROJECTED_ATTRIBUTES`` - Allowed only when querying an index. Retrieves all attributes that have been projected into the index. If the index is configured to project all attributes, this return value is equivalent to specifying ``ALL_ATTRIBUTES`` . 
   
  * ``COUNT`` - Returns the number of matching items, rather than the matching items themselves. 
   
  * ``SPECIFIC_ATTRIBUTES`` - Returns only the attributes listed in *AttributesToGet* . This return value is equivalent to specifying *AttributesToGet* without specifying any value for *select* . If you query a local secondary index and request only attributes that are projected into that index, the operation will read only the index and not the table. If any of the requested attributes are not projected into the local secondary index, DynamoDB will fetch each of these attributes from the parent table. This extra fetching incurs additional throughput cost and latency. If you query a global secondary index, you can only request attributes that are projected into the index. Global secondary index queries cannot fetch attributes from the parent table. 
   

   

  If neither *select* nor *AttributesToGet* are specified, DynamoDB defaults to ``ALL_ATTRIBUTES`` when accessing a table, and ``ALL_PROJECTED_ATTRIBUTES`` when accessing an index. You cannot use both *select* and *AttributesToGet* together in a single request, unless the value for *select* is ``SPECIFIC_ATTRIBUTES`` . (This usage is equivalent to specifying *AttributesToGet* without any value for *select* .)

   

  .. note::

    

    If you use the *projection-expression* parameter, then the value for *select* can only be ``SPECIFIC_ATTRIBUTES`` . Any other value for *select* will return an error.

    

  

  Possible values:

  
  *   ``ALL_ATTRIBUTES``

  
  *   ``ALL_PROJECTED_ATTRIBUTES``

  
  *   ``SPECIFIC_ATTRIBUTES``

  
  *   ``COUNT``

  

  

``--attributes-to-get`` (list)


  .. warning::

    

    This is a legacy parameter, for backward compatibility. New applications should use *projection-expression* instead. Do not combine legacy parameters and expression parameters in a single API call; otherwise, DynamoDB will return a *ValidationException* exception.

     

    This parameter allows you to retrieve attributes of type List or Map; however, it cannot retrieve individual elements within a List or a Map.

    

   

  The names of one or more attributes to retrieve. If no attribute names are provided, then all attributes will be returned. If any of the requested attributes are not found, they will not appear in the result.

   

  Note that *AttributesToGet* has no effect on provisioned throughput consumption. DynamoDB determines capacity units consumed based on item size, not on the amount of data that is returned to an application.

   

  You cannot use both *AttributesToGet* and *select* together in a *query* request, *unless* the value for *select* is ``SPECIFIC_ATTRIBUTES`` . (This usage is equivalent to specifying *AttributesToGet* without any value for *select* .)

   

  If you query a local secondary index and request only attributes that are projected into that index, the operation will read only the index and not the table. If any of the requested attributes are not projected into the local secondary index, DynamoDB will fetch each of these attributes from the parent table. This extra fetching incurs additional throughput cost and latency.

   

  If you query a global secondary index, you can only request attributes that are projected into the index. Global secondary index queries cannot fetch attributes from the parent table.

  



Syntax::

  "string" "string" ...



``--consistent-read`` | ``--no-consistent-read`` (boolean)


  Determines the read consistency model: If set to ``true`` , then the operation uses strongly consistent reads; otherwise, the operation uses eventually consistent reads.

   

  Strongly consistent reads are not supported on global secondary indexes. If you query a global secondary index with *no-consistent-read* set to ``true`` , you will receive a *ValidationException* .

  

``--key-conditions`` (map)


  .. warning::

     

    This is a legacy parameter, for backward compatibility. New applications should use *KeyConditionExpression* instead. Do not combine legacy parameters and expression parameters in a single API call; otherwise, DynamoDB will return a *ValidationException* exception.

     

   

  The selection criteria for the query. For a query on a table, you can have conditions only on the table primary key attributes. You must provide the hash key attribute name and value as an ``EQ`` condition. You can optionally provide a second condition, referring to the range key attribute.

   

  .. note::

     

    If you don't provide a range key condition, all of the items that match the hash key will be retrieved. If a *FilterExpression* or *QueryFilter* is present, it will be applied after the items are retrieved.

    

   

  For a query on an index, you can have conditions only on the index key attributes. You must provide the index hash attribute name and value as an ``EQ`` condition. You can optionally provide a second condition, referring to the index key range attribute.

   

  Each *key-conditions* element consists of an attribute name to compare, along with the following:

   

   
  * *AttributeValueList* - One or more values to evaluate against the supplied attribute. The number of values in the list depends on the *ComparisonOperator* being used. For type Number, value comparisons are numeric. String value comparisons for greater than, equals, or less than are based on ASCII character code values. For example, ``a`` is greater than ``A`` , and ``a`` is greater than ``B`` . For a list of code values, see `http\://en.wikipedia.org/wiki/ASCII#ASCII_printable_characters`_ . For Binary, DynamoDB treats each byte of the binary data as unsigned when it compares binary values. 
   
  * *ComparisonOperator* - A comparator for evaluating attributes, for example, equals, greater than, less than, and so on. For *key-conditions* , only the following comparison operators are supported:  ``EQ | LE | LT | GE | GT | BEGINS_WITH | BETWEEN``   The following are descriptions of these comparison operators. 

     
    * ``EQ`` : Equal.  *AttributeValueList* can contain only one *AttributeValue* of type String, Number, or Binary (not a set type). If an item contains an *AttributeValue* element of a different type than the one specified in the request, the value does not match. For example, ``{"S":"6"}`` does not equal ``{"N":"6"}`` . Also, ``{"N":"6"}`` does not equal ``{"NS":["6", "2", "1"]}`` .  
     
    * ``LE`` : Less than or equal.  *AttributeValueList* can contain only one *AttributeValue* element of type String, Number, or Binary (not a set type). If an item contains an *AttributeValue* element of a different type than the one provided in the request, the value does not match. For example, ``{"S":"6"}`` does not equal ``{"N":"6"}`` . Also, ``{"N":"6"}`` does not compare to ``{"NS":["6", "2", "1"]}`` .  
     
    * ``LT`` : Less than.  *AttributeValueList* can contain only one *AttributeValue* of type String, Number, or Binary (not a set type). If an item contains an *AttributeValue* element of a different type than the one provided in the request, the value does not match. For example, ``{"S":"6"}`` does not equal ``{"N":"6"}`` . Also, ``{"N":"6"}`` does not compare to ``{"NS":["6", "2", "1"]}`` .  
     
    * ``GE`` : Greater than or equal.  *AttributeValueList* can contain only one *AttributeValue* element of type String, Number, or Binary (not a set type). If an item contains an *AttributeValue* element of a different type than the one provided in the request, the value does not match. For example, ``{"S":"6"}`` does not equal ``{"N":"6"}`` . Also, ``{"N":"6"}`` does not compare to ``{"NS":["6", "2", "1"]}`` .  
     
    * ``GT`` : Greater than.  *AttributeValueList* can contain only one *AttributeValue* element of type String, Number, or Binary (not a set type). If an item contains an *AttributeValue* element of a different type than the one provided in the request, the value does not match. For example, ``{"S":"6"}`` does not equal ``{"N":"6"}`` . Also, ``{"N":"6"}`` does not compare to ``{"NS":["6", "2", "1"]}`` .  
     
    * ``BEGINS_WITH`` : Checks for a prefix.  *AttributeValueList* can contain only one *AttributeValue* of type String or Binary (not a Number or a set type). The target attribute of the comparison must be of type String or Binary (not a Number or a set type).  
     
    * ``BETWEEN`` : Greater than or equal to the first value, and less than or equal to the second value.  *AttributeValueList* must contain two *AttributeValue* elements of the same type, either String, Number, or Binary (not a set type). A target attribute matches if the target value is greater than, or equal to, the first element and less than, or equal to, the second element. If an item contains an *AttributeValue* element of a different type than the one provided in the request, the value does not match. For example, ``{"S":"6"}`` does not compare to ``{"N":"6"}`` . Also, ``{"N":"6"}`` does not compare to ``{"NS":["6", "2", "1"]}``  
     

   
   

   

  For usage examples of *AttributeValueList* and *ComparisonOperator* , see `Legacy Conditional Parameters`_ in the *Amazon DynamoDB Developer Guide* .

  



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



``--query-filter`` (map)


  .. warning::

     

    This is a legacy parameter, for backward compatibility. New applications should use *FilterExpression* instead. Do not combine legacy parameters and expression parameters in a single API call; otherwise, DynamoDB will return a *ValidationException* exception.

     

   

  A condition that evaluates the query results after the items are read and returns only the desired values.

   

  This parameter does not support attributes of type List or Map.

   

  .. note::

    

    A *QueryFilter* is applied after the items have already been read; the process of filtering does not consume any additional read capacity units.

    

   

  If you provide more than one condition in the *QueryFilter* map, then by default all of the conditions must evaluate to true. In other words, the conditions are ANDed together. (You can use the *conditional-operator* parameter to OR the conditions instead. If you do this, then at least one of the conditions must evaluate to true, rather than all of them.)

   

  Note that *QueryFilter* does not allow key attributes. You cannot define a filter condition on a hash key or range key.

   

  Each *QueryFilter* element consists of an attribute name to compare, along with the following:

   

   
  * *AttributeValueList* - One or more values to evaluate against the supplied attribute. The number of values in the list depends on the operator specified in *ComparisonOperator* . For type Number, value comparisons are numeric. String value comparisons for greater than, equals, or less than are based on ASCII character code values. For example, ``a`` is greater than ``A`` , and ``a`` is greater than ``B`` . For a list of code values, see `http\://en.wikipedia.org/wiki/ASCII#ASCII_printable_characters`_ . For type Binary, DynamoDB treats each byte of the binary data as unsigned when it compares binary values. For information on specifying data types in JSON, see `JSON Data Format`_ in the *Amazon DynamoDB Developer Guide* . 
   
  * *ComparisonOperator* - A comparator for evaluating attributes. For example, equals, greater than, less than, etc. The following comparison operators are available: ``EQ | NE | LE | LT | GE | GT | NOT_NULL | NULL | CONTAINS | NOT_CONTAINS | BEGINS_WITH | IN | BETWEEN``  For complete descriptions of all comparison operators, see the `Condition`_ data type. 
   

  



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

     

   

  A logical operator to apply to the conditions in a *QueryFilter* map:

   

   
  * ``AND`` - If all of the conditions evaluate to true, then the entire map evaluates to true.
   
  * ``OR`` - If at least one of the conditions evaluate to true, then the entire map evaluates to true.
   

   

  If you omit *conditional-operator* , then ``AND`` is the default.

   

  The operation will succeed only if the entire map evaluates to true.

   

  .. note::

    

    This parameter does not support attributes of type List or Map.

    

  

  Possible values:

  
  *   ``AND``

  
  *   ``OR``

  

  

``--scan-index-forward`` | ``--no-scan-index-forward`` (boolean)


  Specifies the order in which to return the query results - either ascending (``true`` ) or descending (``false`` ).

   

  Items with the same hash key are stored in sorted order by range key .If the range key data type is Number, the results are stored in numeric order. For type String, the results are returned in order of ASCII character code values. For type Binary, DynamoDB treats each byte of the binary data as unsigned.

   

  If *ScanIndexForward* is ``true`` , DynamoDB returns the results in order, by range key. This is the default behavior.

   

  If *ScanIndexForward* is ``false`` , DynamoDB sorts the results in descending order by range key, and then returns the results to the client.

  

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

    

  

``--filter-expression`` (string)


  A string that contains conditions that DynamoDB applies after the *query* operation, but before the data is returned to you. Items that do not satisfy the *FilterExpression* criteria are not returned.

   

  .. note::

     

    A *FilterExpression* is applied after the items have already been read; the process of filtering does not consume any additional read capacity units.

     

   

  For more information, see `Filter Expressions`_ in the *Amazon DynamoDB Developer Guide* .

   

  .. note::

    

    *FilterExpression* replaces the legacy *QueryFilter* and *conditional-operator* parameters.

    

  

``--key-condition-expression`` (string)


  The condition that specifies the key value(s) for items to be retrieved by the *query* action.

   

  The condition must perform an equality test on a single hash key value. The condition can also perform one of several comparison tests on a single range key value. *query* can use *KeyConditionExpression* to retrieve one item with a given hash and range key value, or several items that have the same hash key value but different range key values.

   

  The hash key equality test is required, and must be specified in the following format:

   

   ``hashAttributeName``  *=*  ``:hashval``  

   

  If you also want to provide a range key condition, it must be combined using *AND* with the hash key condition. Following is an example, using the **=** comparison operator for the range key:

   

   ``hashAttributeName``  *=*  ``:hashval``  *AND*  ``rangeAttributeName``  *=*  ``:rangeval``  

   

  Valid comparisons for the range key condition are as follows:

   

   
  * ``rangeAttributeName``  *=*  ``:rangeval`` - true if the range key is equal to ``:rangeval`` . 
   
  * ``rangeAttributeName``  **  ``:rangeval`` - true if the range key is less than ``:rangeval`` . 
   
  * ``rangeAttributeName``  *=*  ``:rangeval`` - true if the range key is less than or equal to ``:rangeval`` . 
   
  * ``rangeAttributeName``  **  ``:rangeval`` - true if the range key is greater than ``:rangeval`` . 
   
  * ``rangeAttributeName``  *=* ``:rangeval`` - true if the range key is greater than or equal to ``:rangeval`` . 
   
  * ``rangeAttributeName``  *BETWEEN*  ``:rangeval1``  *AND*  ``:rangeval2`` - true if the range key is greater than or equal to ``:rangeval1`` , and less than or equal to ``:rangeval2`` . 
   
  * *begins_with (* ``rangeAttributeName`` , ``:rangeval`` *)* - true if the range key begins with a particular operand. (You cannot use this function with a range key that is of type Number.) Note that the function name ``begins_with`` is case-sensitive. 
   

   

  Use the *ExpressionAttributeValues* parameter to replace tokens such as ``:hashval`` and ``:rangeval`` with actual values at runtime.

   

  You can optionally use the *ExpressionAttributeNames* parameter to replace the names of the hash and range attributes with placeholder tokens. This option might be necessary if an attribute name conflicts with a DynamoDB reserved word. For example, the following *KeyConditionExpression* parameter causes an error because *Size* is a reserved word:

   

   
  * ``Size = :myval``  
   

   

  To work around this, define a placeholder (such a ``#S`` ) to represent the attribute name *Size* . *KeyConditionExpression* then is as follows:

   

   
  * ``#S = :myval``  
   

   

  For a list of reserved words, see `Reserved Words`_ in the *Amazon DynamoDB Developer Guide* .

   

  For more information on *ExpressionAttributeNames* and *ExpressionAttributeValues* , see `Using Placeholders for Attribute Names and Values`_ in the *Amazon DynamoDB Developer Guide* .

   

  .. note::

     

    *KeyConditionExpression* replaces the legacy *key-conditions* parameter.

     

  

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

**To query an item**

This example queries items in the *MusicCollection* table. The table has a hash-and-range primary key (*Artist* and *SongTitle*), but this query only specifies the hash key value. It returns song titles by the artist named "No One You Know".

Command::

  aws dynamodb query --table-name MusicCollection --key-conditions file://key-conditions.json --projection-expression "SongTitle"

The arguments for ``--key-conditions`` are stored in a JSON file, ``key-conditions.json``.  Here are the contents of that file::

  { 
      "Artist": { 
          "AttributeValueList": [ 
              {"S": "No One You Know"}
          ],  
          "ComparisonOperator": "EQ" 
      } 
  }

Output::

  {
      "Count": 2, 
      "Items": [
          {
              "SongTitle": {
                  "S": "Call Me Today"
              }
          }, 
          {
              "SongTitle": {
                  "S": "Scared of My Shadow"
              }
          }
      ], 
      "ScannedCount": 2, 
      "ConsumedCapacity": null
  }


======
Output
======

Items -> (list)

  

  An array of item attributes that match the query criteria. Each element in this array consists of an attribute name and the value for that attribute.

  

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

   

  If you used a *QueryFilter* in the request, then *Count* is the number of items returned after the filter was applied, and *ScannedCount* is the number of matching items beforethe filter was applied.

   

  If you did not use a filter in the request, then *Count* and *ScannedCount* are the same.

  

  

ScannedCount -> (integer)

  

  The number of items evaluated, before any *QueryFilter* is applied. A high *ScannedCount* value with few, or no, *Count* results indicates an inefficient *query* operation. For more information, see `Count and ScannedCount`_ in the *Amazon DynamoDB Developer Guide* .

   

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
.. _Legacy Conditional Parameters: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/LegacyConditionalParameters.html
.. _JSON Data Format: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DataFormat.html
.. _Accessing Item Attributes: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Expressions.AccessingItemAttributes.html
.. _Count and ScannedCount: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/QueryAndScan.html#Count
.. _Specifying Conditions: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Expressions.SpecifyingConditions.html
.. _Using Placeholders for Attribute Names and Values: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ExpressionPlaceholders.html
.. _http\://en.wikipedia.org/wiki/ASCII#ASCII_printable_characters: http://en.wikipedia.org/wiki/ASCII#ASCII_printable_characters
.. _Condition: http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_Condition.html
