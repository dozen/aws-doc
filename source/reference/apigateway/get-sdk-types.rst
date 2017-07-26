[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-sdk-types:


*************
get-sdk-types
*************



===========
Description
===========



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/GetSdkTypes>`_


========
Synopsis
========

::

    get-sdk-types
  [--position <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--position`` (string)


  The current pagination position in the paged result set.

  

``--limit`` (integer)


  The maximum number of returned results per page.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

position -> (string)

  

  

items -> (list)

  

  The current page of elements from this collection.

  

  (structure)

    

    A type of SDK that API Gateway can generate.

    

    id -> (string)

      

      The identifier of an  SdkType instance.

      

      

    friendlyName -> (string)

      

      The user-friendly name of an  SdkType instance.

      

      

    description -> (string)

      

      The description of an  SdkType .

      

      

    configurationProperties -> (list)

      

      A list of configuration properties of an  SdkType .

      

      (structure)

        

        A configuration property of an SDK type.

        

        name -> (string)

          

          The name of a an  SdkType configuration property.

          

          

        friendlyName -> (string)

          

          The user-friendly name of an  SdkType configuration property.

          

          

        description -> (string)

          

          The description of an  SdkType configuration property.

          

          

        required -> (boolean)

          

          A boolean flag of an  SdkType configuration property to indicate if the associated SDK configuration property is required (``true`` ) or not (``false`` ).

          

          

        defaultValue -> (string)

          

          The default value of an  SdkType configuration property.

          

          

        

      

    

  

