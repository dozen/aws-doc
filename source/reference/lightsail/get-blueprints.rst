[ :ref:`aws <cli:aws>` . :ref:`lightsail <cli:aws lightsail>` ]

.. _cli:aws lightsail get-blueprints:


**************
get-blueprints
**************



===========
Description
===========



Returns the list of available instance images, or *blueprints* . You can use a blueprint to create a new virtual private server already running a specific operating system, as well as a preinstalled app or development stack. The software each instance is running depends on the blueprint image you choose.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lightsail-2016-11-28/GetBlueprints>`_


``get-blueprints`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``blueprints``


========
Synopsis
========

::

    get-blueprints
  [--include-inactive | --no-include-inactive]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--include-inactive`` | ``--no-include-inactive`` (boolean)


  A Boolean value indicating whether to include inactive results in your request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON page-token provided. The JSON page-token follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

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

blueprints -> (list)

  

  An array of key-value pairs that contains information about the available blueprints.

  

  (structure)

    

    Describes a blueprint (a virtual private server image).

    

    blueprintId -> (string)

      

      The ID for the virtual private server image (e.g., ``app_wordpress_4_4`` or ``app_lamp_7_0`` ).

      

      

    name -> (string)

      

      The friendly name of the blueprint (e.g., ``Amazon Linux`` ).

      

      

    group -> (string)

      

      The group name of the blueprint (e.g., ``amazon-linux`` ).

      

      

    type -> (string)

      

      The type of the blueprint (e.g., ``os`` or ``app`` ).

      

      

    description -> (string)

      

      The description of the blueprint.

      

      

    isActive -> (boolean)

      

      A Boolean value indicating whether the blueprint is active. When you update your blueprints, you will inactivate old blueprints and keep the most recent versions active.

      

      

    minPower -> (integer)

      

      The minimum machine size required to run this blueprint. ``0`` indicates that the blueprint runs on all instances.

      

      

    version -> (string)

      

      The version number of the operating system, application, or stack (e.g., ``2016.03.0`` ).

      

      

    versionCode -> (string)

      

      The version code.

      

      

    productUrl -> (string)

      

      The product URL to learn more about the image or blueprint.

      

      

    licenseUrl -> (string)

      

      The end-user license agreement URL for the image or blueprint.

      

      

    

  

nextPageToken -> (string)

  

  A token used for advancing to the next page of results from your get blueprints request.

  

  

