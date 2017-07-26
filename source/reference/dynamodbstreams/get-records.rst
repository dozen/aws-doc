[ :ref:`aws <cli:aws>` . :ref:`dynamodbstreams <cli:aws dynamodbstreams>` ]

.. _cli:aws dynamodbstreams get-records:


***********
get-records
***********



===========
Description
===========



Retrieves the stream records from a given shard.

 

Specify a shard iterator using the ``shard-iterator`` parameter. The shard iterator specifies the position in the shard from which you want to start reading stream records sequentially. If there are no stream records available in the portion of the shard that the iterator points to, ``get-records`` returns an empty list. Note that it might take multiple calls to get to a portion of the shard that contains stream records.

 

.. note::

  

  get-recordscan retrieve a maximum of 1 MB of data or 2000 stream records, whichever comes first.

  



========
Synopsis
========

::

    get-records
  --shard-iterator <value>
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--shard-iterator`` (string)


  A shard iterator that was retrieved from a previous get-shard-iterator operation. This iterator can be used to access the stream records in this shard.

  

``--limit`` (integer)


  The maximum number of records to return from the shard. The upper limit is 1000.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Records -> (list)

  

  The stream records from the shard, which were retrieved using the shard iterator.

  

  (structure)

    

    A description of a unique event within a stream.

    

    eventID -> (string)

      

      A globally unique identifier for the event that was recorded in this stream record.

      

      

    eventName -> (string)

      

      The type of data modification that was performed on the DynamoDB table:

       

       
      * ``INSERT`` - a new item was added to the table.
       
      * ``MODIFY`` - one or more of the item's attributes were updated.
       
      * ``REMOVE`` - the item was deleted from the table
       

      

      

    eventVersion -> (string)

      

      The version number of the stream record format. Currently, this is *1.0* .

      

      

    eventSource -> (string)

      

      The AWS service from which the stream record originated. For DynamoDB Streams, this is *aws:dynamodb* .

      

      

    awsRegion -> (string)

      

      The region in which the *get-records* request was received.

      

      

    dynamodb -> (structure)

      

      The main body of the stream record, containing all of the DynamoDB-specific fields.

      

      Keys -> (map)

        

        The primary key attribute(s) for the DynamoDB item that was modified.

        

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

            

            A Map data type.

            

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

                

                A Map data type.

                

                key -> (string)

                  

                  

                ( ... recursive ... )

              L -> (list)

                

                A List data type.

                

                ( ... recursive ... )

              NULL -> (boolean)

                

                A Null data type.

                

                

              BOOL -> (boolean)

                

                A Boolean data type.

                

                

              

            

          L -> (list)

            

            A List data type.

            

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

                

                A Map data type.

                

                key -> (string)

                  

                  

                ( ... recursive ... )

              L -> (list)

                

                A List data type.

                

                ( ... recursive ... )

              NULL -> (boolean)

                

                A Null data type.

                

                

              BOOL -> (boolean)

                

                A Boolean data type.

                

                

              

            

          NULL -> (boolean)

            

            A Null data type.

            

            

          BOOL -> (boolean)

            

            A Boolean data type.

            

            

          

        

      NewImage -> (map)

        

        The item in the DynamoDB table as it appeared after it was modified.

        

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

            

            A Map data type.

            

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

                

                A Map data type.

                

                key -> (string)

                  

                  

                ( ... recursive ... )

              L -> (list)

                

                A List data type.

                

                ( ... recursive ... )

              NULL -> (boolean)

                

                A Null data type.

                

                

              BOOL -> (boolean)

                

                A Boolean data type.

                

                

              

            

          L -> (list)

            

            A List data type.

            

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

                

                A Map data type.

                

                key -> (string)

                  

                  

                ( ... recursive ... )

              L -> (list)

                

                A List data type.

                

                ( ... recursive ... )

              NULL -> (boolean)

                

                A Null data type.

                

                

              BOOL -> (boolean)

                

                A Boolean data type.

                

                

              

            

          NULL -> (boolean)

            

            A Null data type.

            

            

          BOOL -> (boolean)

            

            A Boolean data type.

            

            

          

        

      OldImage -> (map)

        

        The item in the DynamoDB table as it appeared before it was modified.

        

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

            

            A Map data type.

            

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

                

                A Map data type.

                

                key -> (string)

                  

                  

                ( ... recursive ... )

              L -> (list)

                

                A List data type.

                

                ( ... recursive ... )

              NULL -> (boolean)

                

                A Null data type.

                

                

              BOOL -> (boolean)

                

                A Boolean data type.

                

                

              

            

          L -> (list)

            

            A List data type.

            

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

                

                A Map data type.

                

                key -> (string)

                  

                  

                ( ... recursive ... )

              L -> (list)

                

                A List data type.

                

                ( ... recursive ... )

              NULL -> (boolean)

                

                A Null data type.

                

                

              BOOL -> (boolean)

                

                A Boolean data type.

                

                

              

            

          NULL -> (boolean)

            

            A Null data type.

            

            

          BOOL -> (boolean)

            

            A Boolean data type.

            

            

          

        

      SequenceNumber -> (string)

        

        The sequence number of the stream record.

        

        

      SizeBytes -> (long)

        

        The size of the stream record, in bytes.

        

        

      StreamViewType -> (string)

        

        The type of data from the modified DynamoDB item that was captured in this stream record:

         

         
        * ``KEYS_ONLY`` - only the key attributes of the modified item.
         
        * ``NEW_IMAGE`` - the entire item, as it appears after it was modified.
         
        * ``OLD_IMAGE`` - the entire item, as it appeared before it was modified.
         
        * ``NEW_AND_OLD_IMAGES`` — both the new and the old item images of the item.
         

        

        

      

    

  

NextShardIterator -> (string)

  

  The next position in the shard from which to start sequentially reading stream records. If set to ``null`` , the shard has been closed and the requested iterator will not return any more data.

  

  

