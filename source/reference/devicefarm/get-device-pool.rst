[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm get-device-pool:


***************
get-device-pool
***************



===========
Description
===========



Gets information about a device pool.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/devicefarm-2015-06-23/GetDevicePool>`_


========
Synopsis
========

::

    get-device-pool
  --arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--arn`` (string)


  The device pool's ARN.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

devicePool -> (structure)

  

  An object containing information about the requested device pool.

  

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

        

        The rule's stringified attribute. For example, specify the value as ``"\"abc\""`` .

         

        Allowed values include:

         

         
        * ARN: The ARN. 
         
        * FORM_FACTOR: The form factor (for example, phone or tablet). 
         
        * MANUFACTURER: The manufacturer. 
         
        * PLATFORM: The platform (for example, Android or iOS). 
         
        * REMOTE_ACCESS_ENABLED: Whether the device is enabled for remote access. 
         
        * APPIUM_VERSION: The Appium version for the test. 
         

        

        

      operator -> (string)

        

        The rule's operator.

         

         
        * EQUALS: The equals operator. 
         
        * GREATER_THAN: The greater-than operator. 
         
        * IN: The in operator. 
         
        * LESS_THAN: The less-than operator. 
         
        * NOT_IN: The not-in operator. 
         
        * CONTAINS: The contains operator. 
         

        

        

      value -> (string)

        

        The rule's value.

        

        

      

    

  

