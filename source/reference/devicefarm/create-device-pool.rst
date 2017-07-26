[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm create-device-pool:


******************
create-device-pool
******************



===========
Description
===========



Creates a device pool.



========
Synopsis
========

::

    create-device-pool
  --project-arn <value>
  --name <value>
  [--description <value>]
  --rules <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--project-arn`` (string)


  The ARN of the project for the device pool.

  

``--name`` (string)


  The device pool's name.

  

``--description`` (string)


  The device pool's description.

  

``--rules`` (list)


  The device pool's rules.

  



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

  

  The newly created device pool.

  

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

        

        

      

    

  

