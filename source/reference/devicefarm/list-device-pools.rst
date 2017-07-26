[ :ref:`aws <cli:aws>` . :ref:`devicefarm <cli:aws devicefarm>` ]

.. _cli:aws devicefarm list-device-pools:


*****************
list-device-pools
*****************



===========
Description
===========



Gets information about device pools.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/devicefarm-2015-06-23/ListDevicePools>`_


``list-device-pools`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``devicePools``


========
Synopsis
========

::

    list-device-pools
  --arn <value>
  [--type <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




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

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

          

          

        

      

    

  

nextToken -> (string)

  

  If the number of items that are returned is significantly large, this is an identifier that is also returned, which can be used in a subsequent call to this operation to return the next set of items in the list.

  

  

