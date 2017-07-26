[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm update-device-pool:


******************
update-device-pool
******************



===========
Description
===========



Modifies the name, description, and rules in a device pool given the attributes and the pool ARN. Rule updates are all-or-nothing, meaning they can only be updated as a whole (or not at all).



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
  [--generate-cli-skeleton]




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
      "attribute": "ARN"|"PLATFORM"|"FORM_FACTOR"|"MANUFACTURER",
      "operator": "EQUALS"|"LESS_THAN"|"GREATER_THAN"|"IN"|"NOT_IN",
      "value": "string"
    }
    ...
  ]



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

        

        

      

    

  

