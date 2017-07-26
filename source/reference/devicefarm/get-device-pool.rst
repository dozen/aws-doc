[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm get-device-pool:


***************
get-device-pool
***************



===========
Description
===========



Gets information about a device pool.



========
Synopsis
========

::

    get-device-pool
  --arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--arn`` (string)


  The device pool's ARN.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

devicePool -> (structure)

  

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

        

        

      

    

  

