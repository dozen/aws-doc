[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-deployments:


***************
get-deployments
***************



===========
Description
===========



Gets information about a  Deployments collection.



``get-deployments`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``items``


========
Synopsis
========

::

    get-deployments
  --rest-api-id <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--rest-api-id`` (string)


  The identifier of the  RestApi resource for the collection of  Deployment resources to get information about.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

position -> (string)

  

  

items -> (list)

  

  The current page of any  Deployment resources in the collection of deployment resources.

  

  (structure)

    

    An immutable representation of a  RestApi resource that can be called by users using  Stages . A deployment must be associated with a  Stage for it to be callable over the Internet.

    

    id -> (string)

      

      The identifier for the deployment resource.

      

      

    description -> (string)

      

      The description for the deployment resource.

      

      

    createdDate -> (timestamp)

      

      The date and time that the deployment resource was created.

      

      

    apiSummary -> (map)

      

      Gets a summary of the  RestApi at the date and time that the deployment resource was created.

      

      key -> (string)

        

        

      value -> (map)

        

        key -> (string)

          

          

        value -> (structure)

          

          Represents a summary of a  Method resource, given a particular date and time.

          

          authorizationType -> (string)

            

            Specifies the type of authorization used for the method.

            

            

          apiKeyRequired -> (boolean)

            

            Specifies whether the method requires a valid  ApiKey .

            

            

          

        

      

    

  

