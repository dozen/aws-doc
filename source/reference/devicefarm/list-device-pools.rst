[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm list-device-pools:


*****************
list-device-pools
*****************



===========
Description
===========



Gets information about device pools.



========
Synopsis
========

::

    list-device-pools
  --arn <value>
  [--type <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--arn`` (string)


  The project ARN.

  

``--type`` (string)


  The device pools' type.

   

  Allowed values include:

   

   
  * CURATED: A device pool that is created and managed by AWS Device Farm.
   
  * PRIVATE: A device pool that is created and managed by the device pool developer.
   

  

  Possible values:

  
  *   ``CURATED``

  
  *   ``PRIVATE``

  

  

``--next-token`` (string)


  An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

devicePools -> (list)

  

  Information about the device pools.

  

  (structure)

    

    Represents a collection of device types.

    

    arn -> (string)

      

      The device pool's ARN.

      

      

    name -> (string)

      

      The device pool's name.

      

      

    description -> (string)

      

      The device pool's description.

      

      

    type -> (string)

      

      The device pool's type.

       

      Allowed values include:

       

       
      * CURATED: A device pool that is created and managed by AWS Device Farm.
       
      * PRIVATE: A device pool that is created and managed by the device pool developer.
       

      

      

    rules -> (list)

      

      Information about the device pool's rules.

      

      (structure)

        

        Represents a condition for a device pool.

        

        attribute -> (string)

          

          The rule's attribute.

           

          Allowed values include:

           

           
          * ARN: The ARN.
           
          * FORM_FACTOR: The form factor (for example, phone or tablet).
           
          * MANUFACTURER: The manufacturer.
           
          * PLATFORM: The platform (for example, Android or iOS).
           

          

          

        operator -> (string)

          

          The rule's operator.

           

           
          * EQUALS: The equals operator.
           
          * GREATER_THAN: The greater-than operator.
           
          * IN: The in operator.
           
          * LESS_THAN: The less-than operator.
           
          * NOT_IN: The not-in operator.
           

          

          

        value -> (string)

          

          The rule's value.

          

          

        

      

    

  

nextToken -> (string)

  

  If the number of items that are returned is significantly large, this is an identifier that is also returned, which can be used in a subsequent call to this operation to return the next set of items in the list.

  

  

