[ :ref:`aws <cli:aws>` . :ref:`dynamodb <cli:aws dynamodb>` ]

.. _cli:aws dynamodb query:


*****
query
*****



===========
Description
===========



A ``query`` operation uses the primary key of a table or a secondary index to directly access items from that table or index.

 

Use the ``KeyConditionExpression`` parameter to provide a specific value for the partition key. The ``query`` operation will return all of the items from the table or index with that partition key value. You can optionally narrow the scope of the ``query`` operation by specifying a sort key value and a comparison operator in ``KeyConditionExpression`` . You can use the ``ScanIndexForward`` parameter to get results in forward or reverse order, by sort key.

 

Queries that do not return results consume the minimum number of read capacity units for that type of read operation.

 

If the total number of items meeting the query criteria exceeds the result set size limit of 1 MB, the query stops and results are returned to the user with the ``LastEvaluatedKey`` element to continue the query in a subsequent operation. Unlike a ``scan`` operation, a ``query`` operation never returns both an empty result set and a ``LastEvaluatedKey`` value. ``LastEvaluatedKey`` is only provided if you have used the ``Limit`` parameter, or if the result set exceeds 1 MB (prior to applying a filter). 

 

You can query a table, a local secondary index, or a global secondary index. For a query on a table or on a local secondary index, you can set the ``consistent-read`` parameter to ``true`` and obtain a strongly consistent result. Global secondary indexes support eventually consistent reads only, so do not specify ``consistent-read`` when querying a global secondary index.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dynamodb-2012-08-10/Query>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--table-name`` (string)


  The name of the table containing the requested items.

  

``--index-name`` (string)


  The name of an index to query. This index can be any local secondary index or global secondary index on the table. Note that if you use the ``index-name`` parameter, you must also provide ``TableName.``  

  

``--select`` (string)


  The attributes to be returned in the result. You can retrieve all item attributes, specific item attributes, the count of matching items, or in the case of an index, some or all of the attributes projected into the index.

   

   
  * ``ALL_ATTRIBUTES`` - Returns all of the item attributes from the specified table or index. If you query a local secondary index, then for each matching item in the index DynamoDB will fetch the entire item from the parent table. If the index is configured to project all item attributes, then all of the data can be obtained from the local secondary index, and no fetching is required. 
   
  * ``ALL_PROJECTED_ATTRIBUTES`` - Allowed only when querying an index. Retrieves all attributes that have been projected into the index. If the index is configured to project all attributes, this return value is equivalent to specifying ``ALL_ATTRIBUTES`` . 
   
  * ``COUNT`` - Returns the number of matching items, rather than the matching items themselves. 
   
  * ``SPECIFIC_ATTRIBUTES`` - Returns only the attributes listed in ``AttributesToGet`` . This return value is equivalent to specifying ``AttributesToGet`` without specifying any value for ``select`` . If you query or scan a local secondary index and request only attributes that are projected into that index, the operation will read only the index and not the table. If any of the requested attributes are not projected into the local secondary index, DynamoDB will fetch each of these attributes from the parent table. This extra fetching incurs additional throughput cost and latency. If you query or scan a global secondary index, you can only request attributes that are projected into the index. Global secondary index queries cannot fetch attributes from the parent table. 
   

   

  If neither ``select`` nor ``AttributesToGet`` are specified, DynamoDB defaults to ``ALL_ATTRIBUTES`` when accessing a table, and ``ALL_PROJECTED_ATTRIBUTES`` when accessing an index. You cannot use both ``select`` and ``AttributesToGet`` together in a single request, unless the value for ``select`` is ``SPECIFIC_ATTRIBUTES`` . (This usage is equivalent to specifying ``AttributesToGet`` without any value for ``select`` .)

   

  .. note::

     

    If you use the ``projection-expression`` parameter, then the value for ``select`` can only be ``SPECIFIC_ATTRIBUTES`` . Any other value for ``select`` will return an error.

     

  

  Possible values:

  
  *   ``ALL_ATTRIBUTES``

  
  *   ``ALL_PROJECTED_ATTRIBUTES``

  
  *   ``SPECIFIC_ATTRIBUTES``

  
  *   ``COUNT``

  

  

``--attributes-to-get`` (list)


  This is a legacy parameter. Use ``projection-expression`` instead. For more information, see `AttributesToGet <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/LegacyConditionalParameters.AttributesToGet.html>`_ in the *Amazon DynamoDB Developer Guide* .

  



Syntax::

  "string" "string" ...



``--consistent-read`` | ``--no-consistent-read`` (boolean)


  Determines the read consistency model: If set to ``true`` , then the operation uses strongly consistent reads; otherwise, the operation uses eventually consistent reads.

   

  Strongly consistent reads are not supported on global secondary indexes. If you query a global secondary index with ``consistent-read`` set to ``true`` , you will receive a ``ValidationException`` .

  

``--key-conditions`` (map)


  This is a legacy parameter. Use ``KeyConditionExpression`` instead. For more information, see `key-conditions <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/LegacyConditionalParameters.KeyConditions.html>`_ in the *Amazon DynamoDB Developer Guide* .

  



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


  This is a legacy parameter. Use ``FilterExpression`` instead. For more information, see `QueryFilter <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/LegacyConditionalParameters.QueryFilter.html>`_ in the *Amazon DynamoDB Developer Guide* .

  



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


  This is a legacy parameter. Use ``FilterExpression`` instead. For more information, see `conditional-operator <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/LegacyConditionalParameters.ConditionalOperator.html>`_ in the *Amazon DynamoDB Developer Guide* .

  

  Possible values:

  
  *   ``AND``

  
  *   ``OR``

  

  

``--scan-index-forward`` | ``--no-scan-index-forward`` (boolean)


  Specifies the order for index traversal: If ``true`` (default), the traversal is performed in ascending order; if ``false`` , the traversal is performed in descending order. 

   

  Items with the same partition key value are stored in sorted order by sort key. If the sort key data type is Number, the results are stored in numeric order. For type String, the results are stored in order of ASCII character code values. For type Binary, DynamoDB treats each byte of the binary data as unsigned.

   

  If ``ScanIndexForward`` is ``true`` , DynamoDB returns the results in the order in which they are stored (by sort key value). This is the default behavior. If ``ScanIndexForward`` is ``false`` , DynamoDB reads the results in reverse order by sort key value, and then returns the results to the client.

  

``--return-consumed-capacity`` (string)


  Determines the level of detail about provisioned throughput consumption that is returned in the response:

   

   
  * ``INDEXES`` - The response includes the aggregate ``ConsumedCapacity`` for the operation, together with ``ConsumedCapacity`` for each table and secondary index that was accessed. Note that some operations, such as ``get-item`` and ``batch-get-item`` , do not access any indexes at all. In these cases, specifying ``INDEXES`` will only return ``ConsumedCapacity`` information for table(s). 
   
  * ``TOTAL`` - The response includes only the aggregate ``ConsumedCapacity`` for the operation. 
   
  * ``NONE`` - No ``ConsumedCapacity`` details are included in the response. 
   

  

  Possible values:

  
  *   ``INDEXES``

  
  *   ``TOTAL``

  
  *   ``NONE``

  

  

``--projection-expression`` (string)


  A string that identifies one or more attributes to retrieve from the table. These attributes can include scalars, sets, or elements of a JSON document. The attributes in the expression must be separated by commas.

   

  If no attribute names are specified, then all attributes will be returned. If any of the requested attributes are not found, they will not appear in the result.

   

  For more information, see `Accessing Item Attributes <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Expressions.AccessingItemAttributes.html>`_ in the *Amazon DynamoDB Developer Guide* .

  

``--filter-expression`` (string)


  A string that contains conditions that DynamoDB applies after the ``query`` operation, but before the data is returned to you. Items that do not satisfy the ``FilterExpression`` criteria are not returned.

   

  A ``FilterExpression`` does not allow key attributes. You cannot define a filter expression based on a partition key or a sort key.

   

  .. note::

     

    A ``FilterExpression`` is applied after the items have already been read; the process of filtering does not consume any additional read capacity units.

     

   

  For more information, see `Filter Expressions <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/QueryAndScan.html#FilteringResults>`_ in the *Amazon DynamoDB Developer Guide* .

  

``--key-condition-expression`` (string)


  The condition that specifies the key value(s) for items to be retrieved by the ``query`` action.

   

  The condition must perform an equality test on a single partition key value. The condition can also perform one of several comparison tests on a single sort key value. ``query`` can use ``KeyConditionExpression`` to retrieve one item with a given partition key value and sort key value, or several items that have the same partition key value but different sort key values.

   

  The partition key equality test is required, and must be specified in the following format:

   

   ``partitionKeyName``  *=*  ``:partitionkeyval``  

   

  If you also want to provide a condition for the sort key, it must be combined using ``AND`` with the condition for the sort key. Following is an example, using the **=** comparison operator for the sort key:

   

   ``partitionKeyName``  ``=``  ``:partitionkeyval``  ``AND``  ``sortKeyName``  ``=``  ``:sortkeyval``  

   

  Valid comparisons for the sort key condition are as follows:

   

   
  * ``sortKeyName``  ``=``  ``:sortkeyval`` - true if the sort key value is equal to ``:sortkeyval`` . 
   
  * ``sortKeyName``  ````  ``:sortkeyval`` - true if the sort key value is less than ``:sortkeyval`` . 
   
  * ``sortKeyName``  ``=``  ``:sortkeyval`` - true if the sort key value is less than or equal to ``:sortkeyval`` . 
   
  * ``sortKeyName``  ````  ``:sortkeyval`` - true if the sort key value is greater than ``:sortkeyval`` . 
   
  * ``sortKeyName``  ``=``  ``:sortkeyval`` - true if the sort key value is greater than or equal to ``:sortkeyval`` . 
   
  * ``sortKeyName``  ``BETWEEN``  ``:sortkeyval1``  ``AND``  ``:sortkeyval2`` - true if the sort key value is greater than or equal to ``:sortkeyval1`` , and less than or equal to ``:sortkeyval2`` . 
   
  * ``begins_with (``  ``sortKeyName`` , ``:sortkeyval``  ``)`` - true if the sort key value begins with a particular operand. (You cannot use this function with a sort key that is of type Number.) Note that the function name ``begins_with`` is case-sensitive. 
   

   

  Use the ``ExpressionAttributeValues`` parameter to replace tokens such as ``:partitionval`` and ``:sortval`` with actual values at runtime.

   

  You can optionally use the ``ExpressionAttributeNames`` parameter to replace the names of the partition key and sort key with placeholder tokens. This option might be necessary if an attribute name conflicts with a DynamoDB reserved word. For example, the following ``KeyConditionExpression`` parameter causes an error because *Size* is a reserved word:

   

   
  * ``Size = :myval``   
   

   

  To work around this, define a placeholder (such a ``#S`` ) to represent the attribute name *Size* . ``KeyConditionExpression`` then is as follows:

   

   
  * ``#S = :myval``   
   

   

  For a list of reserved words, see `Reserved Words <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ReservedWords.html>`_ in the *Amazon DynamoDB Developer Guide* .

   

  For more information on ``ExpressionAttributeNames`` and ``ExpressionAttributeValues`` , see `Using Placeholders for Attribute Names and Values <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ExpressionPlaceholders.html>`_ in the *Amazon DynamoDB Developer Guide* .

  

``--expression-attribute-names`` (map)


  One or more substitution tokens for attribute names in an expression. The following are some use cases for using ``ExpressionAttributeNames`` :

   

   
  * To access an attribute whose name conflicts with a DynamoDB reserved word. 
   
  * To create a placeholder for repeating occurrences of an attribute name in an expression. 
   
  * To prevent special characters in an attribute name from being misinterpreted in an expression. 
   

   

  Use the **#** character in an expression to dereference an attribute name. For example, consider the following attribute name:

   

   
  * ``Percentile``   
   

   

  The name of this attribute conflicts with a reserved word, so it cannot be used directly in an expression. (For the complete list of reserved words, see `Reserved Words <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ReservedWords.html>`_ in the *Amazon DynamoDB Developer Guide* ). To work around this, you could specify the following for ``ExpressionAttributeNames`` :

   

   
  * ``{"#P":"Percentile"}``   
   

   

  You could then use this substitution in an expression, as in this example:

   

   
  * ``#P = :val``   
   

   

  .. note::

     

    Tokens that begin with the **:** character are *expression attribute values* , which are placeholders for the actual value at runtime.

     

   

  For more information on expression attribute names, see `Accessing Item Attributes <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Expressions.AccessingItemAttributes.html>`_ in the *Amazon DynamoDB Developer Guide* .

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--expression-attribute-values`` (map)


  One or more values that can be substituted in an expression.

   

  Use the **:** (colon) character in an expression to dereference an attribute value. For example, suppose that you wanted to check whether the value of the *ProductStatus* attribute was one of the following: 

   

   ``Available | Backordered | Discontinued``  

   

  You would first need to specify ``ExpressionAttributeValues`` as follows:

   

   ``{ ":avail":{"S":"Available"}, ":back":{"S":"Backordered"}, ":disc":{"S":"Discontinued"} }``  

   

  You could then use these values in an expression, such as this:

   

   ``ProductStatus IN (:avail, :back, :disc)``  

   

  For more information on expression attribute values, see `Specifying Conditions <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Expressions.SpecifyingConditions.html>`_ in the *Amazon DynamoDB Developer Guide* .

  



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

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To query an item**

This example queries items in the *MusicCollection* table. The table has a hash-and-range primary key (*Artist* and *SongTitle*), but this query only specifies the hash key value. It returns song titles by the artist named "No One You Know".

Command::

  aws dynamodb query --table-name MusicCollection --projection-expression "SongTitle" --key-condition-expression "Artist = :v1" --expression-attribute-values file://expression-attributes.json


The arguments for ``--expression-attribute-values`` are stored in a JSON file named ``expression-attributes.json``::

  {
    ":v1": {"S": "No One You Know"}
  }

Output::

  {
      "Count": 2,
      "Items": [
          {
              "SongTitle": {
                  "S": "Call Me Today"
              },
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

        

        

      

    

  

Count -> (integer)

  

  The number of items in the response.

   

  If you used a ``QueryFilter`` in the request, then ``Count`` is the number of items returned after the filter was applied, and ``ScannedCount`` is the number of matching items before the filter was applied.

   

  If you did not use a filter in the request, then ``Count`` and ``ScannedCount`` are the same.

  

  

ScannedCount -> (integer)

  

  The number of items evaluated, before any ``QueryFilter`` is applied. A high ``ScannedCount`` value with few, or no, ``Count`` results indicates an inefficient ``query`` operation. For more information, see `Count and ScannedCount <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/QueryAndScan.html#Count>`_ in the *Amazon DynamoDB Developer Guide* .

   

  If you did not use a filter in the request, then ``ScannedCount`` is the same as ``Count`` .

  

  

LastEvaluatedKey -> (map)

  

  The primary key of the item where the operation stopped, inclusive of the previous result set. Use this value to start a new operation, excluding this value in the new request.

   

  If ``LastEvaluatedKey`` is empty, then the "last page" of results has been processed and there is no more data to be retrieved.

   

  If ``LastEvaluatedKey`` is not empty, it does not necessarily mean that there is more data in the result set. The only way to know when you have reached the end of the result set is when ``LastEvaluatedKey`` is empty.

  

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

      

      

    

  

ConsumedCapacity -> (structure)

  

  The capacity units consumed by the ``query`` operation. The data returned includes the total provisioned throughput consumed, along with statistics for the table and any indexes involved in the operation. ``ConsumedCapacity`` is only returned if the ``return-consumed-capacity`` parameter was specified For more information, see `Provisioned Throughput <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ProvisionedThroughputIntro.html>`_ in the *Amazon DynamoDB Developer Guide* .

  

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

        

        

      

    

  

