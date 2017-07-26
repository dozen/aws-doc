[ :ref:`aws <cli:aws>` . :ref:`ecr <cli:aws ecr>` ]

.. _cli:aws ecr describe-repositories:


*********************
describe-repositories
*********************



===========
Description
===========



Describes image repositories in a registry.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecr-2015-09-21/DescribeRepositories>`_


``describe-repositories`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``repositories``


========
Synopsis
========

::

    describe-repositories
  [--registry-id <value>]
  [--repository-names <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--registry-id`` (string)


  The AWS account ID associated with the registry that contains the repositories to be described. If you do not specify a registry, the default registry is assumed.

  

``--repository-names`` (list)


  A list of repositories to describe. If this parameter is omitted, then all repositories in a registry are described.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``next-token`` is provided in the command's output. To resume pagination, provide the ``next-token`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``next-token`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe the repositories in a registry**

This example describes the repositories in the default registry for an account.

Command::

  aws ecr describe-repositories

Output::

  {
      "repositories": [
          {
              "registryId": "012345678910",
              "repositoryName": "ubuntu",
              "repositoryArn": "arn:aws:ecr:us-west-2:012345678910:repository/ubuntu"
          },
          {
              "registryId": "012345678910",
              "repositoryName": "test",
              "repositoryArn": "arn:aws:ecr:us-west-2:012345678910:repository/test"
          }
      ]
  }


======
Output
======

repositories -> (list)

  

  A list of repository objects corresponding to valid repositories.

  

  (structure)

    

    An object representing a repository.

    

    repositoryArn -> (string)

      

      The Amazon Resource Name (ARN) that identifies the repository. The ARN contains the ``arn:aws:ecr`` namespace, followed by the region of the repository, the AWS account ID of the repository owner, the repository namespace, and then the repository name. For example, ``arn:aws:ecr:region:012345678910:repository/test`` .

      

      

    registryId -> (string)

      

      The AWS account ID associated with the registry that contains the repository.

      

      

    repositoryName -> (string)

      

      The name of the repository.

      

      

    repositoryUri -> (string)

      

      The URI for the repository. You can use this URI for Docker ``push`` and ``pull`` operations.

      

      

    createdAt -> (timestamp)

      

      The date and time, in JavaScript date/time format, when the repository was created.

      

      

    

  

nextToken -> (string)

  

  The ``nextToken`` value to include in a future ``describe-repositories`` request. When the results of a ``describe-repositories`` request exceed ``maxResults`` , this value can be used to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

