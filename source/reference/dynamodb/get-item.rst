[ :ref:`aws <cli:aws>` . :ref:`dynamodb <cli:aws dynamodb>` ]

.. _cli:aws dynamodb get-item:


********
get-item
********



===========
Description
===========



The ``get-item`` operation returns a set of attributes for the item with the given primary key. If there is no matching item, ``get-item`` does not return any data and there will be no ``Item`` element in the response.

 

 ``get-item`` provides an eventually consistent read by default. If your application requires a strongly consistent read, set ``consistent-read`` to ``true`` . Although a strongly consistent read might take more time than an eventually consistent read, it always returns the last updated value.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dynamodb-2012-08-10/GetItem>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--table-name`` (string)


  The name of the table containing the requested item.

  

``--key`` (map)


  A map of attribute names to ``AttributeValue`` objects, representing the primary key of the item to retrieve.

   

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



``--attributes-to-get`` (list)


  This is a legacy parameter. Use ``projection-expression`` instead. For more information, see `AttributesToGet <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/LegacyConditionalParameters.AttributesToGet.html>`_ in the *Amazon DynamoDB Developer Guide* .

  



Syntax::

  "string" "string" ...



``--consistent-read`` | ``--no-consistent-read`` (boolean)


  Determines the read consistency model: If set to ``true`` , then the operation uses strongly consistent reads; otherwise, the operation uses eventually consistent reads.

  

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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To read an item in a table**

This example retrieves an item from the *MusicCollection* table. The table has a hash-and-range primary key (*Artist* and *SongTitle*), so you must specify both of these attributes.


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

  

  A map of attribute names to ``AttributeValue`` objects, as specified by ``projection-expression`` .

  

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

  

  The capacity units consumed by the ``get-item`` operation. The data returned includes the total provisioned throughput consumed, along with statistics for the table and any indexes involved in the operation. ``ConsumedCapacity`` is only returned if the ``return-consumed-capacity`` parameter was specified. For more information, see `Provisioned Throughput <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ProvisionedThroughputIntro.html>`_ in the *Amazon DynamoDB Developer Guide* .

  

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

        

        

      

    

  

