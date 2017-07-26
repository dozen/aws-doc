[ :ref:`aws <cli:aws>` . :ref:`dynamodb <cli:aws dynamodb>` ]

.. _cli:aws dynamodb update-item:


***********
update-item
***********



===========
Description
===========



Edits an existing item's attributes, or adds a new item to the table if it does not already exist. You can put, delete, or add attribute values. You can also perform a conditional update on an existing item (insert a new attribute name-value pair if it doesn't exist, or replace an existing name-value pair if it has certain expected attribute values). If conditions are specified and the item does not exist, then the operation fails and a new item is not created. 

 

You can also return the item's attribute values in the same *update-item* operation using the *ReturnValues* parameter.



========
Synopsis
========

::

    update-item
  --table-name <value>
  --key <value>
  [--attribute-updates <value>]
  [--expected <value>]
  [--conditional-operator <value>]
  [--return-values <value>]
  [--return-consumed-capacity <value>]
  [--return-item-collection-metrics <value>]
  [--update-expression <value>]
  [--condition-expression <value>]
  [--expression-attribute-names <value>]
  [--expression-attribute-values <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--table-name`` (string)


  The name of the table containing the item to update. 

  

``--key`` (map)


  The primary key of the item to be updated. Each element consists of an attribute name and a value for that attribute.

   

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



``--attribute-updates`` (map)


  .. warning::

     

    This is a legacy parameter, for backward compatibility. New applications should use *update-expression* instead. Do not combine legacy parameters and expression parameters in a single API call; otherwise, DynamoDB will return a *ValidationException* exception.

     

    This parameter can be used for modifying top-level attributes; however, it does not support individual list or map elements.

     

   

  The names of attributes to be modified, the action to perform on each, and the new value for each. If you are updating an attribute that is an index key attribute for any indexes on that table, the attribute type must match the index key type defined in the *AttributesDefinition* of the table description. You can use *update-item* to update any nonkey attributes.

   

  Attribute values cannot be null. String and Binary type attributes must have lengths greater than zero. Set type attributes must not be empty. Requests with empty values will be rejected with a *ValidationException* exception.

   

  Each *attribute-updates* element consists of an attribute name to modify, along with the following:

   

   
  * *Value* - The new value, if applicable, for this attribute. 
   
  * *Action* - A value that specifies how to perform the update. This action is only valid for an existing attribute whose data type is Number or is a set; do not use ``ADD`` for other data types.  If an item with the specified primary key is found in the table, the following values perform the following actions: 

     
    * ``PUT`` - Adds the specified attribute to the item. If the attribute already exists, it is replaced by the new value.  
     
    * ``DELETE`` - Removes the attribute and its value, if no value is specified for ``DELETE`` . The data type of the specified value must match the existing value's data type. If a set of values is specified, then those values are subtracted from the old set. For example, if the attribute value was the set ``[a,b,c]`` and the ``DELETE`` action specifies ``[a,c]`` , then the final attribute value is ``[b]`` . Specifying an empty set is an error. 
     
    * ``ADD`` - Adds the specified value to the item, if the attribute does not already exist. If the attribute does exist, then the behavior of ``ADD`` depends on the data type of the attribute: 

       
      * If the existing attribute is a number, and if *Value* is also a number, then *Value* is mathematically added to the existing attribute. If *Value* is a negative number, then it is subtracted from the existing attribute. 

      .. note::

         If you use ``ADD`` to increment or decrement a number value for an item that doesn't exist before the update, DynamoDB uses 0 as the initial value. Similarly, if you use ``ADD`` for an existing item to increment or decrement an attribute value that doesn't exist before the update, DynamoDB uses ``0`` as the initial value. For example, suppose that the item you want to update doesn't have an attribute named *itemcount* , but you decide to ``ADD`` the number ``3`` to this attribute anyway. DynamoDB will create the *itemcount* attribute, set its initial value to ``0`` , and finally add ``3`` to it. The result will be a new *itemcount* attribute, with a value of ``3`` . 

       
       
      * If the existing data type is a set, and if *Value* is also a set, then *Value* is appended to the existing set. For example, if the attribute value is the set ``[1,2]`` , and the ``ADD`` action specified ``[3]`` , then the final attribute value is ``[1,2,3]`` . An error occurs if an ``ADD`` action is specified for a set attribute and the attribute type specified does not match the existing set type.  Both sets must have the same primitive data type. For example, if the existing data type is a set of strings, *Value* must also be a set of strings. 
       

     
     

   

  If no item with the specified key is found in the table, the following values perform the following actions: 

   

     
    * ``PUT`` - Causes DynamoDB to create a new item with the specified primary key, and then adds the attribute.  
     
    * ``DELETE`` - Nothing happens, because attributes cannot be deleted from a nonexistent item. The operation succeeds, but DynamoDB does not create a new item. 
     
    * ``ADD`` - Causes DynamoDB to create an item with the supplied primary key and number (or set of numbers) for the attribute value. The only data types allowed are Number and Number Set. 
     

   
   

   

  If you provide any attributes that are part of an index key, then the data types for those attributes must match those of the schema in the table's attribute definition.

  



JSON Syntax::

  {"string": {
        "Value": {
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
        },
        "Action": "ADD"|"PUT"|"DELETE"
      }
    ...}



``--expected`` (map)


  .. warning::

     

    This is a legacy parameter, for backward compatibility. New applications should use *condition-expression* instead. Do not combine legacy parameters and expression parameters in a single API call; otherwise, DynamoDB will return a *ValidationException* exception.

     

   

  A map of attribute/condition pairs. *Expected* provides a conditional block for the *update-item* operation.

   

  Each element of *Expected* consists of an attribute name, a comparison operator, and one or more values. DynamoDB compares the attribute with the value(s) you supplied, using the comparison operator. For each *Expected* element, the result of the evaluation is either true or false.

   

  If you specify more than one element in the *Expected* map, then by default all of the conditions must evaluate to true. In other words, the conditions are ANDed together. (You can use the *conditional-operator* parameter to OR the conditions instead. If you do this, then at least one of the conditions must evaluate to true, rather than all of them.)

   

  If the *Expected* map evaluates to true, then the conditional operation succeeds; otherwise, it fails.

   

  *Expected* contains the following:

   

   
  * *AttributeValueList* - One or more values to evaluate against the supplied attribute. The number of values in the list depends on the *ComparisonOperator* being used. For type Number, value comparisons are numeric. String value comparisons for greater than, equals, or less than are based on ASCII character code values. For example, ``a`` is greater than ``A`` , and ``a`` is greater than ``B`` . For a list of code values, see `http\://en.wikipedia.org/wiki/ASCII#ASCII_printable_characters`_ . For type Binary, DynamoDB treats each byte of the binary data as unsigned when it compares binary values. 
   
  * *ComparisonOperator* - A comparator for evaluating attributes in the *AttributeValueList* . When performing the comparison, DynamoDB uses strongly consistent reads. The following comparison operators are available: ``EQ | NE | LE | LT | GE | GT | NOT_NULL | NULL | CONTAINS | NOT_CONTAINS | BEGINS_WITH | IN | BETWEEN``  The following are descriptions of each comparison operator. 

     
    * ``EQ`` : Equal. ``EQ`` is supported for all datatypes, including lists and maps. *AttributeValueList* can contain only one *AttributeValue* element of type String, Number, Binary, String Set, Number Set, or Binary Set. If an item contains an *AttributeValue* element of a different type than the one provided in the request, the value does not match. For example, ``{"S":"6"}`` does not equal ``{"N":"6"}`` . Also, ``{"N":"6"}`` does not equal ``{"NS":["6", "2", "1"]}`` .  
     
    * ``NE`` : Not equal. ``NE`` is supported for all datatypes, including lists and maps. *AttributeValueList* can contain only one *AttributeValue* of type String, Number, Binary, String Set, Number Set, or Binary Set. If an item contains an *AttributeValue* of a different type than the one provided in the request, the value does not match. For example, ``{"S":"6"}`` does not equal ``{"N":"6"}`` . Also, ``{"N":"6"}`` does not equal ``{"NS":["6", "2", "1"]}`` .  
     
    * ``LE`` : Less than or equal.  *AttributeValueList* can contain only one *AttributeValue* element of type String, Number, or Binary (not a set type). If an item contains an *AttributeValue* element of a different type than the one provided in the request, the value does not match. For example, ``{"S":"6"}`` does not equal ``{"N":"6"}`` . Also, ``{"N":"6"}`` does not compare to ``{"NS":["6", "2", "1"]}`` .  
     
    * ``LT`` : Less than.  *AttributeValueList* can contain only one *AttributeValue* of type String, Number, or Binary (not a set type). If an item contains an *AttributeValue* element of a different type than the one provided in the request, the value does not match. For example, ``{"S":"6"}`` does not equal ``{"N":"6"}`` . Also, ``{"N":"6"}`` does not compare to ``{"NS":["6", "2", "1"]}`` .  
     
    * ``GE`` : Greater than or equal.  *AttributeValueList* can contain only one *AttributeValue* element of type String, Number, or Binary (not a set type). If an item contains an *AttributeValue* element of a different type than the one provided in the request, the value does not match. For example, ``{"S":"6"}`` does not equal ``{"N":"6"}`` . Also, ``{"N":"6"}`` does not compare to ``{"NS":["6", "2", "1"]}`` .  
     
    * ``GT`` : Greater than.  *AttributeValueList* can contain only one *AttributeValue* element of type String, Number, or Binary (not a set type). If an item contains an *AttributeValue* element of a different type than the one provided in the request, the value does not match. For example, ``{"S":"6"}`` does not equal ``{"N":"6"}`` . Also, ``{"N":"6"}`` does not compare to ``{"NS":["6", "2", "1"]}`` .  
     
    * ``NOT_NULL`` : The attribute exists. ``NOT_NULL`` is supported for all datatypes, including lists and maps. 

    .. note::

      This operator tests for the existence of an attribute, not its data type. If the data type of attribute "``a`` " is null, and you evaluate it using ``NOT_NULL`` , the result is a Boolean *true* . This result is because the attribute "``a`` " exists; its data type is not relevant to the ``NOT_NULL`` comparison operator. 

     
     
    * ``NULL`` : The attribute does not exist. ``NULL`` is supported for all datatypes, including lists and maps. 

    .. note::

      This operator tests for the nonexistence of an attribute, not its data type. If the data type of attribute "``a`` " is null, and you evaluate it using ``NULL`` , the result is a Boolean *false* . This is because the attribute "``a`` " exists; its data type is not relevant to the ``NULL`` comparison operator. 

     
     
    * ``CONTAINS`` : Checks for a subsequence, or value in a set. *AttributeValueList* can contain only one *AttributeValue* element of type String, Number, or Binary (not a set type). If the target attribute of the comparison is of type String, then the operator checks for a substring match. If the target attribute of the comparison is of type Binary, then the operator looks for a subsequence of the target that matches the input. If the target attribute of the comparison is a set ("``SS`` ", "``NS`` ", or "``BS`` "), then the operator evaluates to true if it finds an exact match with any member of the set. CONTAINS is supported for lists: When evaluating "``a CONTAINS b`` ", "``a`` " can be a list; however, "``b`` " cannot be a set, a map, or a list. 
     
    * ``NOT_CONTAINS`` : Checks for absence of a subsequence, or absence of a value in a set. *AttributeValueList* can contain only one *AttributeValue* element of type String, Number, or Binary (not a set type). If the target attribute of the comparison is a String, then the operator checks for the absence of a substring match. If the target attribute of the comparison is Binary, then the operator checks for the absence of a subsequence of the target that matches the input. If the target attribute of the comparison is a set ("``SS`` ", "``NS`` ", or "``BS`` "), then the operator evaluates to true if it *does not* find an exact match with any member of the set. NOT_CONTAINS is supported for lists: When evaluating "``a NOT CONTAINS b`` ", "``a`` " can be a list; however, "``b`` " cannot be a set, a map, or a list. 
     
    * ``BEGINS_WITH`` : Checks for a prefix.  *AttributeValueList* can contain only one *AttributeValue* of type String or Binary (not a Number or a set type). The target attribute of the comparison must be of type String or Binary (not a Number or a set type).  
     
    * ``IN`` : Checks for matching elements within two sets. *AttributeValueList* can contain one or more *AttributeValue* elements of type String, Number, or Binary (not a set type). These attributes are compared against an existing set type attribute of an item. If any elements of the input set are present in the item attribute, the expression evaluates to true. 
     
    * ``BETWEEN`` : Greater than or equal to the first value, and less than or equal to the second value.  *AttributeValueList* must contain two *AttributeValue* elements of the same type, either String, Number, or Binary (not a set type). A target attribute matches if the target value is greater than, or equal to, the first element and less than, or equal to, the second element. If an item contains an *AttributeValue* element of a different type than the one provided in the request, the value does not match. For example, ``{"S":"6"}`` does not compare to ``{"N":"6"}`` . Also, ``{"N":"6"}`` does not compare to ``{"NS":["6", "2", "1"]}``  
     

   
   

   

  For usage examples of *AttributeValueList* and *ComparisonOperator* , see `Legacy Conditional Parameters`_ in the *Amazon DynamoDB Developer Guide* .

   

  For backward compatibility with previous DynamoDB releases, the following parameters can be used instead of *AttributeValueList* and *ComparisonOperator* :

   

   
  * *Value* - A value for DynamoDB to compare with an attribute. 
   
  * *Exists* - A Boolean value that causes DynamoDB to evaluate the value before attempting the conditional operation: 

     
    * If *Exists* is ``true`` , DynamoDB will check to see if that attribute value already exists in the table. If it is found, then the condition evaluates to true; otherwise the condition evaluate to false. 
     
    * If *Exists* is ``false`` , DynamoDB assumes that the attribute value does *not* exist in the table. If in fact the value does not exist, then the assumption is valid and the condition evaluates to true. If the value is found, despite the assumption that it does not exist, the condition evaluates to false.
     

   

  Note that the default value for *Exists* is ``true`` .

   
   

   

  The *Value* and *Exists* parameters are incompatible with *AttributeValueList* and *ComparisonOperator* . Note that if you use both sets of parameters at once, DynamoDB will return a *ValidationException* exception.

   

  .. note::

    

    This parameter does not support attributes of type List or Map.

    

  



JSON Syntax::

  {"string": {
        "Value": {
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
        },
        "Exists": true|false,
        "ComparisonOperator": "EQ"|"NE"|"IN"|"LE"|"LT"|"GE"|"GT"|"BETWEEN"|"NOT_NULL"|"NULL"|"CONTAINS"|"NOT_CONTAINS"|"BEGINS_WITH",
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
        ]
      }
    ...}



``--conditional-operator`` (string)


  .. warning::

     

    This is a legacy parameter, for backward compatibility. New applications should use *condition-expression* instead. Do not combine legacy parameters and expression parameters in a single API call; otherwise, DynamoDB will return a *ValidationException* exception.

     

   

  A logical operator to apply to the conditions in the *Expected* map:

   

   
  * ``AND`` - If all of the conditions evaluate to true, then the entire map evaluates to true.
   
  * ``OR`` - If at least one of the conditions evaluate to true, then the entire map evaluates to true.
   

   

  If you omit *conditional-operator* , then ``AND`` is the default.

   

  The operation will succeed only if the entire map evaluates to true.

   

  .. note::

    

    This parameter does not support attributes of type List or Map.

    

  

  Possible values:

  
  *   ``AND``

  
  *   ``OR``

  

  

``--return-values`` (string)


  Use *ReturnValues* if you want to get the item attributes as they appeared either before or after they were updated. For *update-item* , the valid values are:

   

   
  * ``NONE`` - If *ReturnValues* is not specified, or if its value is ``NONE`` , then nothing is returned. (This setting is the default for *ReturnValues* .) 
   
  * ``ALL_OLD`` - If *update-item* overwrote an attribute name-value pair, then the content of the old item is returned. 
   
  * ``UPDATED_OLD`` - The old versions of only the updated attributes are returned. 
   
  * ``ALL_NEW`` - All of the attributes of the new version of the item are returned. 
   
  * ``UPDATED_NEW`` - The new versions of only the updated attributes are returned. 
   

  

  Possible values:

  
  *   ``NONE``

  
  *   ``ALL_OLD``

  
  *   ``UPDATED_OLD``

  
  *   ``ALL_NEW``

  
  *   ``UPDATED_NEW``

  

  

``--return-consumed-capacity`` (string)


  Determines the level of detail about provisioned throughput consumption that is returned in the response:

   

   
  * *INDEXES* - The response includes the aggregate *ConsumedCapacity* for the operation, together with *ConsumedCapacity* for each table and secondary index that was accessed. Note that some operations, such as *get-item* and *batch-get-item* , do not access any indexes at all. In these cases, specifying *INDEXES* will only return *ConsumedCapacity* information for table(s). 
   
  * *TOTAL* - The response includes only the aggregate *ConsumedCapacity* for the operation.
   
  * *NONE* - No *ConsumedCapacity* details are included in the response.
   

  

  Possible values:

  
  *   ``INDEXES``

  
  *   ``TOTAL``

  
  *   ``NONE``

  

  

``--return-item-collection-metrics`` (string)


  Determines whether item collection metrics are returned. If set to ``SIZE`` , the response includes statistics about item collections, if any, that were modified during the operation are returned in the response. If set to ``NONE`` (the default), no statistics are returned.

  

  Possible values:

  
  *   ``SIZE``

  
  *   ``NONE``

  

  

``--update-expression`` (string)


  An expression that defines one or more attributes to be updated, the action to be performed on them, and new value(s) for them.

   

  The following action values are available for *update-expression* .

   

   
  * ``SET`` - Adds one or more attributes and values to an item. If any of these attribute already exist, they are replaced by the new values. You can also use ``SET`` to add or subtract from an attribute that is of type Number. For example: ``SET myNum = myNum + :val``  ``SET`` supports the following functions: 

     
    * ``if_not_exists (path, operand)`` - if the item does not contain an attribute at the specified path, then ``if_not_exists`` evaluates to operand; otherwise, it evaluates to path. You can use this function to avoid overwriting an attribute that may already be present in the item.
     
    * ``list_append (operand, operand)`` - evaluates to a list with a new element added to it. You can append the new element to the start or the end of the list by reversing the order of the operands.
     

   

  These function names are case-sensitive.

   
   
  * ``REMOVE`` - Removes one or more attributes from an item. 
   
  * ``ADD`` - Adds the specified value to the item, if the attribute does not already exist. If the attribute does exist, then the behavior of ``ADD`` depends on the data type of the attribute: 

     
    * If the existing attribute is a number, and if *Value* is also a number, then *Value* is mathematically added to the existing attribute. If *Value* is a negative number, then it is subtracted from the existing attribute. 

    .. note::

       If you use ``ADD`` to increment or decrement a number value for an item that doesn't exist before the update, DynamoDB uses ``0`` as the initial value. Similarly, if you use ``ADD`` for an existing item to increment or decrement an attribute value that doesn't exist before the update, DynamoDB uses ``0`` as the initial value. For example, suppose that the item you want to update doesn't have an attribute named *itemcount* , but you decide to ``ADD`` the number ``3`` to this attribute anyway. DynamoDB will create the *itemcount* attribute, set its initial value to ``0`` , and finally add ``3`` to it. The result will be a new *itemcount* attribute in the item, with a value of ``3`` . 

     
     
    * If the existing data type is a set and if *Value* is also a set, then *Value* is added to the existing set. For example, if the attribute value is the set ``[1,2]`` , and the ``ADD`` action specified ``[3]`` , then the final attribute value is ``[1,2,3]`` . An error occurs if an ``ADD`` action is specified for a set attribute and the attribute type specified does not match the existing set type.  Both sets must have the same primitive data type. For example, if the existing data type is a set of strings, the *Value* must also be a set of strings. 
     

   

  .. warning::

    

    The ``ADD`` action only supports Number and set data types. In addition, ``ADD`` can only be used on top-level attributes, not nested attributes.

     

   
   
  * ``DELETE`` - Deletes an element from a set. If a set of values is specified, then those values are subtracted from the old set. For example, if the attribute value was the set ``[a,b,c]`` and the ``DELETE`` action specifies ``[a,c]`` , then the final attribute value is ``[b]`` . Specifying an empty set is an error. 

  .. warning::

    The ``DELETE`` action only supports set data types. In addition, ``DELETE`` can only be used on top-level attributes, not nested attributes. 

   
   

   

  You can have many actions in a single expression, such as the following: ``SET a=:value1, b=:value2 DELETE :value3, :value4, :value5`` 

   

  For more information on update expressions, see `Modifying Items and Attributes`_ in the *Amazon DynamoDB Developer Guide* .

   

  .. note::

    

    *update-expression* replaces the legacy *attribute-updates* parameter.

    

  

``--condition-expression`` (string)


  A condition that must be satisfied in order for a conditional update to succeed.

   

  An expression can contain any of the following:

   

   
  * Functions: ``attribute_exists | attribute_not_exists | attribute_type | contains | begins_with | size``  These function names are case-sensitive. 
   
  * Comparison operators: ``= | | | | = | = | BETWEEN | IN``  
   
  * Logical operators: ``AND | OR | NOT``  
   

   

  For more information on condition expressions, see `Specifying Conditions`_ in the *Amazon DynamoDB Developer Guide* .

   

  .. note::

    

    *condition-expression* replaces the legacy *conditional-operator* and *Expected* parameters.

    

  

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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To update an item in a table**

This example updates an item in the *MusicCollection* table. It adds a new attribute (*Year*) and modifies the *AlbumTitle* attribute.  All of the attributes in the item, as they appear after the update, are returned in the response.


Command::

  aws dynamodb update-item --table-name MusicCollection --key file://key.json --update-expression "SET #Y = :y, #AT = :t" --expression-attribute-names file://expression-attribute-names.json --expression-attribute-values file://expression-attribute-values.json  --return-values ALL_NEW

The arguments for ``--key`` are stored in a JSON file, ``key.json``.  Here are the contents of that file::

  {
      "Artist": {"S": "Acme Band"},
      "SongTitle": {"S": "Happy Day"}
  }


The arguments for ``--expression-attribute-names`` are stored in a JSON file, ``expression-attribute-names.json``.  Here are the contents of that file::

  {
      "#Y":"Year", "#AT":"AlbumTitle"
  }

The arguments for ``--expression-attribute-values`` are stored in a JSON file, ``expression-attribute-values.json``.  Here are the contents of that file::

  {
      ":y":{"N": "2015"},
      ":t":{"S": "Louder Than Ever"}
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

Attributes -> (map)

  

  A map of attribute values as they appeared before the *update-item* operation. This map only appears if *ReturnValues* was specified as something other than ``NONE`` in the request. Each element represents one attribute.

  

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

        

        

      

    

  

ItemCollectionMetrics -> (structure)

  

  Information about item collections, if any, that were affected by the operation. *ItemCollectionMetrics* is only returned if the request asked for it. If the table does not have any local secondary indexes, this information is not returned in the response.

  

  ItemCollectionKey -> (map)

    

    The hash key value of the item collection. This value is the same as the hash key of the item.

    

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

        

        

      

    

  SizeEstimateRangeGB -> (list)

    

    An estimate of item collection size, in gigabytes. This value is a two-element array containing a lower bound and an upper bound for the estimate. The estimate includes the size of all the items in the table, plus the size of all attributes projected into all of the local secondary indexes on that table. Use this estimate to measure whether a local secondary index is approaching its size limit.

     

    The estimate is subject to change over time; therefore, do not rely on the precision or accuracy of the estimate.

    

    (double)

      

      

    

  



.. _Provisioned Throughput: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ProvisionedThroughputIntro.html
.. _Reserved Words: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ReservedWords.html
.. _Legacy Conditional Parameters: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/LegacyConditionalParameters.html
.. _Accessing Item Attributes: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Expressions.AccessingItemAttributes.html
.. _Specifying Conditions: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Expressions.SpecifyingConditions.html
.. _http\://en.wikipedia.org/wiki/ASCII#ASCII_printable_characters: http://en.wikipedia.org/wiki/ASCII#ASCII_printable_characters
.. _Modifying Items and Attributes: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Expressions.Modifying.html
