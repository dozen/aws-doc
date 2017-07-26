[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-deployments:


***************
get-deployments
***************



===========
Description
===========



Gets information about a  Deployments collection.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/GetDeployments>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rest-api-id`` (string)


  The string identifier of the associated  RestApi .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get a list of deployments for a REST API**

Command::

  aws apigateway get-deployments --rest-api-id 1234123412

Output::

  {
      "items": [
          {
              "createdDate": 1453797217, 
              "id": "0a2b4c", 
              "description": "Deployed my API for the first time"
          }
      ]
  }



======
Output
======

position -> (string)

  

  

items -> (list)

  

  The current page of elements from this collection.

  

  (structure)

    

    An immutable representation of a  RestApi resource that can be called by users using  Stages . A deployment must be associated with a  Stage for it to be callable over the Internet.

     To create a deployment, call ``POST`` on the  Deployments resource of a  RestApi . To view, update, or delete a deployment, call ``GET`` , ``PATCH`` , or ``DELETE`` on the specified deployment resource (``/restapis/{restapi_id}/deployments/{deployment_id}`` ).  RestApi ,  Deployments ,  Stage , `AWS CLI <http://docs.aws.amazon.com/cli/latest/reference/apigateway/get-deployment.html>`_ , `AWS SDKs <https://aws.amazon.com/tools/>`_  

    id -> (string)

      

      The identifier for the deployment resource.

      

      

    description -> (string)

      

      The description for the deployment resource.

      

      

    createdDate -> (timestamp)

      

      The date and time that the deployment resource was created.

      

      

    apiSummary -> (map)

      

      A summary of the  RestApi at the date and time that the deployment resource was created.

      

      key -> (string)

        

        

      value -> (map)

        

        key -> (string)

          

          

        value -> (structure)

          

          Represents a summary of a  Method resource, given a particular date and time.

          

          authorizationType -> (string)

            

            The method's authorization type. Valid values are ``NONE`` for open access, ``AWS_IAM`` for using AWS IAM permissions, ``CUSTOM`` for using a custom authorizer, or ``COGNITO_USER_POOLS`` for using a Cognito user pool.

            

            

          apiKeyRequired -> (boolean)

            

            Specifies whether the method requires a valid  ApiKey .

            

            

          

        

      

    

  

