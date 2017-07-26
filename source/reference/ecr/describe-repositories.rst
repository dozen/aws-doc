[ :ref:`aws <cli:aws>` . :ref:`ecr <cli:aws ecr>` ]

.. _cli:aws ecr describe-repositories:


*********************
describe-repositories
*********************



===========
Description
===========



Describes image repositories in a registry.



========
Synopsis
========

::

    describe-repositories
  [--registry-id <value>]
  [--repository-names <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--registry-id`` (string)


  The AWS account ID associated with the registry that contains the repositories to be described. If you do not specify a registry, the default registry is assumed.

  

``--repository-names`` (list)


  A list of repositories to describe. If this parameter is omitted, then all repositories in a registry are described. 

  



Syntax::

  "string" "string" ...



``--next-token`` (string)


  The ``nextToken`` value returned from a previous paginated ``describe-repositories`` request where ``maxResults`` was used and the results exceeded the value of that parameter. Pagination continues from the end of the previous results that returned the ``nextToken`` value. This value is ``null`` when there are no more results to return.

  

``--max-results`` (integer)


  The maximum number of repository results returned by ``describe-repositories`` in paginated output. When this parameter is used, ``describe-repositories`` only returns ``maxResults`` results in a single page along with a ``nextToken`` response element. The remaining results of the initial request can be seen by sending another ``describe-repositories`` request with the returned ``nextToken`` value. This value can be between 1 and 100. If this parameter is not used, then ``describe-repositories`` returns up to 100 results and a ``nextToken`` value, if applicable.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

    

    Object representing a repository.

    

    repositoryArn -> (string)

      

      The Amazon Resource Name (ARN) that identifies the repository. The ARN contains the ``arn:aws:ecr`` namespace, followed by the region of the repository, the AWS account ID of the repository owner, the repository namespace, and then the repository name. For example, ``arn:aws:ecr:region:012345678910:repository/test`` .

      

      

    registryId -> (string)

      

      The AWS account ID associated with the registry that contains the repository.

      

      

    repositoryName -> (string)

      

      The name of the repository.

      

      

    

  

nextToken -> (string)

  

  The ``nextToken`` value to include in a future ``describe-repositories`` request. When the results of a ``describe-repositories`` request exceed ``maxResults`` , this value can be used to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

