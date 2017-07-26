[ :ref:`aws <cli:aws>` . :ref:`codecommit <cli:aws codecommit>` ]

.. _cli:aws codecommit list-repositories:


*****************
list-repositories
*****************



===========
Description
===========



Gets information about one or more repositories.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codecommit-2015-04-13/ListRepositories>`_


``list-repositories`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``repositories``


========
Synopsis
========

::

    list-repositories
  [--sort-by <value>]
  [--order <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--sort-by`` (string)


  The criteria used to sort the results of a list repositories operation.

  

  Possible values:

  
  *   ``repositoryName``

  
  *   ``lastModifiedDate``

  

  

``--order`` (string)


  The order in which to sort the results of a list repositories operation.

  

  Possible values:

  
  *   ``ascending``

  
  *   ``descending``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``next-token`` is provided in the command's output. To resume pagination, provide the ``next-token`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``next-token`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To view a list of repositories**

This example lists all AWS CodeCommit repositories associated with the user's AWS account.

Command::

  aws codecommit list-repositories

Output::

  {
    "repositories": [
        {
           "repositoryName": "MyDemoRepo"
           "repositoryId": "f7579e13-b83e-4027-aaef-650c0EXAMPLE",
        },
        {
           "repositoryName": "MyOtherDemoRepo"
           "repositoryId": "cfc29ac4-b0cb-44dc-9990-f6f51EXAMPLE"
        }
    ]
  }

======
Output
======

repositories -> (list)

  

  Lists the repositories called by the list repositories operation.

  

  (structure)

    

    Information about a repository name and ID.

    

    repositoryName -> (string)

      

      The name associated with the repository.

      

      

    repositoryId -> (string)

      

      The ID associated with the repository.

      

      

    

  

nextToken -> (string)

  

  An enumeration token that allows the operation to batch the results of the operation. Batch sizes are 1,000 for list repository operations. When the client sends the token back to AWS CodeCommit, another page of 1,000 records is retrieved.

  

  

