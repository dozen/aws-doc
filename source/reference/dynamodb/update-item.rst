[ :ref:`aws <cli:aws>` . :ref:`dynamodb <cli:aws dynamodb>` ]

.. _cli:aws dynamodb update-item:


***********
update-item
***********



===========
Description
===========



Edits an existing item's attributes, or adds a new item to the table if it does not already exist. You can put, delete, or add attribute values. You can also perform a conditional update on an existing item (insert a new attribute name-value pair if it doesn't exist, or replace an existing name-value pair if it has certain expected attribute values).

 

You can also return the item's attribute values in the same ``update-item`` operation using the ``ReturnValues`` parameter.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dynamodb-2012-08-10/UpdateItem>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--table-name`` (string)


  The name of the table containing the item to update.

  

``--key`` (map)


  The primary key of the item to be updated. Each element consists of an attribute name and a value for that attribute.

   

  For the primary key, you must provide all of the attributes. For example, with a simple primary key, you only need to provide a value for the partition key. For a composite primary key, you must provide values for both the partition key and the sort key.

  



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


  This is a legacy parameter. Use ``update-expression`` instead. For more information, see `attribute-updates <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/LegacyConditionalParameters.AttributeUpdates.html>`_ in the *Amazon DynamoDB Developer Guide* .

  



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


  This is a legacy parameter. Use ``ConditionExpresssion`` instead. For more information, see `Expected <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/LegacyConditionalParameters.Expected.html>`_ in the *Amazon DynamoDB Developer Guide* .

  



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


  This is a legacy parameter. Use ``condition-expression`` instead. For more information, see `conditional-operator <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/LegacyConditionalParameters.ConditionalOperator.html>`_ in the *Amazon DynamoDB Developer Guide* .

  

  Possible values:

  
  *   ``AND``

  
  *   ``OR``

  

  

``--return-values`` (string)


  Use ``ReturnValues`` if you want to get the item attributes as they appeared either before or after they were updated. For ``update-item`` , the valid values are:

   

   
  * ``NONE`` - If ``ReturnValues`` is not specified, or if its value is ``NONE`` , then nothing is returned. (This setting is the default for ``ReturnValues`` .) 
   
  * ``ALL_OLD`` - Returns all of the attributes of the item, as they appeared before the update-item operation. 
   
  * ``UPDATED_OLD`` - Returns only the updated attributes, as they appeared before the update-item operation. 
   
  * ``ALL_NEW`` - Returns all of the attributes of the item, as they appear after the update-item operation. 
   
  * ``UPDATED_NEW`` - Returns only the updated attributes, as they appear after the update-item operation. 
   

   

  There is no additional cost associated with requesting a return value aside from the small network and processing overhead of receiving a larger response. No Read Capacity Units are consumed.

   

  Values returned are strongly consistent

  

  Possible values:

  
  *   ``NONE``

  
  *   ``ALL_OLD``

  
  *   ``UPDATED_OLD``

  
  *   ``ALL_NEW``

  
  *   ``UPDATED_NEW``

  

  

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

  

  

``--update-expression`` (string)


  An expression that defines one or more attributes to be updated, the action to be performed on them, and new value(s) for them.

   

  The following action values are available for ``update-expression`` .

   

   
  * ``SET`` - Adds one or more attributes and values to an item. If any of these attribute already exist, they are replaced by the new values. You can also use ``SET`` to add or subtract from an attribute that is of type Number. For example: ``SET myNum = myNum + :val``    ``SET`` supports the following functions: 

     
    * ``if_not_exists (path, operand)`` - if the item does not contain an attribute at the specified path, then ``if_not_exists`` evaluates to operand; otherwise, it evaluates to path. You can use this function to avoid overwriting an attribute that may already be present in the item. 
     
    * ``list_append (operand, operand)`` - evaluates to a list with a new element added to it. You can append the new element to the start or the end of the list by reversing the order of the operands. 
     

   

  These function names are case-sensitive.

   
   
  * ``REMOVE`` - Removes one or more attributes from an item. 
   
  * ``ADD`` - Adds the specified value to the item, if the attribute does not already exist. If the attribute does exist, then the behavior of ``ADD`` depends on the data type of the attribute: 

     
    * If the existing attribute is a number, and if ``Value`` is also a number, then ``Value`` is mathematically added to the existing attribute. If ``Value`` is a negative number, then it is subtracted from the existing attribute. 

    .. note::

       If you use ``ADD`` to increment or decrement a number value for an item that doesn't exist before the update, DynamoDB uses ``0`` as the initial value. Similarly, if you use ``ADD`` for an existing item to increment or decrement an attribute value that doesn't exist before the update, DynamoDB uses ``0`` as the initial value. For example, suppose that the item you want to update doesn't have an attribute named *itemcount* , but you decide to ``ADD`` the number ``3`` to this attribute anyway. DynamoDB will create the *itemcount* attribute, set its initial value to ``0`` , and finally add ``3`` to it. The result will be a new *itemcount* attribute in the item, with a value of ``3`` . 

     
     
    * If the existing data type is a set and if ``Value`` is also a set, then ``Value`` is added to the existing set. For example, if the attribute value is the set ``[1,2]`` , and the ``ADD`` action specified ``[3]`` , then the final attribute value is ``[1,2,3]`` . An error occurs if an ``ADD`` action is specified for a set attribute and the attribute type specified does not match the existing set type.  Both sets must have the same primitive data type. For example, if the existing data type is a set of strings, the ``Value`` must also be a set of strings. 
     

   

  .. warning::

     

    The ``ADD`` action only supports Number and set data types. In addition, ``ADD`` can only be used on top-level attributes, not nested attributes.

     

   
   
  * ``DELETE`` - Deletes an element from a set. If a set of values is specified, then those values are subtracted from the old set. For example, if the attribute value was the set ``[a,b,c]`` and the ``DELETE`` action specifies ``[a,c]`` , then the final attribute value is ``[b]`` . Specifying an empty set is an error. 

  .. warning::

     The ``DELETE`` action only supports set data types. In addition, ``DELETE`` can only be used on top-level attributes, not nested attributes. 

   
   

   

  You can have many actions in a single expression, such as the following: ``SET a=:value1, b=:value2 DELETE :value3, :value4, :value5``  

   

  For more information on update expressions, see `Modifying Items and Attributes <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Expressions.Modifying.html>`_ in the *Amazon DynamoDB Developer Guide* .

  

``--condition-expression`` (string)


  A condition that must be satisfied in order for a conditional update to succeed.

   

  An expression can contain any of the following:

   

   
  * Functions: ``attribute_exists | attribute_not_exists | attribute_type | contains | begins_with | size``   These function names are case-sensitive. 
   
  * Comparison operators: ``= | | | | = | = | BETWEEN | IN``   
   
  * Logical operators: ``AND | OR | NOT``   
   

   

  For more information on condition expressions, see `Specifying Conditions <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Expressions.SpecifyingConditions.html>`_ in the *Amazon DynamoDB Developer Guide* .

  

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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  A map of attribute values as they appeared before the ``update-item`` operation. This map only appears if ``ReturnValues`` was specified as something other than ``NONE`` in the request. Each element represents one attribute.

  

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

  

  The capacity units consumed by the ``update-item`` operation. The data returned includes the total provisioned throughput consumed, along with statistics for the table and any indexes involved in the operation. ``ConsumedCapacity`` is only returned if the ``return-consumed-capacity`` parameter was specified. For more information, see `Provisioned Throughput <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ProvisionedThroughputIntro.html>`_ in the *Amazon DynamoDB Developer Guide* .

  

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

  

  Information about item collections, if any, that were affected by the ``update-item`` operation. ``ItemCollectionMetrics`` is only returned if the ``return-item-collection-metrics`` parameter was specified. If the table does not have any local secondary indexes, this information is not returned in the response.

   

  Each ``ItemCollectionMetrics`` element consists of:

   

   
  * ``ItemCollectionKey`` - The partition key value of the item collection. This is the same as the partition key value of the item itself. 
   
  * ``SizeEstimateRange`` - An estimate of item collection size, in gigabytes. This value is a two-element array containing a lower bound and an upper bound for the estimate. The estimate includes the size of all the items in the table, plus the size of all attributes projected into all of the local secondary indexes on that table. Use this estimate to measure whether a local secondary index is approaching its size limit. The estimate is subject to change over time; therefore, do not rely on the precision or accuracy of the estimate. 
   

  

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

      

      

    

  

