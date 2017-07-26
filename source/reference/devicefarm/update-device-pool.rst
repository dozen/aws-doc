[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm update-device-pool:


******************
update-device-pool
******************



===========
Description
===========



Modifies the name, description, and rules in a device pool given the attributes and the pool ARN. Rule updates are all-or-nothing, meaning they can only be updated as a whole (or not at all).



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/devicefarm-2015-06-23/UpdateDevicePool>`_


========
Synopsis
========

::

    update-device-pool
  --arn <value>
  [--name <value>]
  [--description <value>]
  [--rules <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--arn`` (string)


  The Amazon Resourc name (ARN) of the Device Farm device pool you wish to update.

  

``--name`` (string)


  A string representing the name of the device pool you wish to update.

  

``--description`` (string)


  A description of the device pool you wish to update.

  

``--rules`` (list)


  Represents the rules you wish to modify for the device pool. Updating rules is optional; however, if you choose to update rules for your request, the update will replace the existing rules.

  



Shorthand Syntax::

    attribute=string,operator=string,value=string ...




JSON Syntax::

  [
    {
      "attribute": "ARN"|"PLATFORM"|"FORM_FACTOR"|"MANUFACTURER"|"REMOTE_ACCESS_ENABLED"|"APPIUM_VERSION",
      "operator": "EQUALS"|"LESS_THAN"|"GREATER_THAN"|"IN"|"NOT_IN"|"CONTAINS",
      "value": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

devicePool -> (structure)

  

  The device pool you just updated.

  

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

        

        

      

    

  

