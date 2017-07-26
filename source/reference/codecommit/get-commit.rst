[ :ref:`aws <cli:aws>` . :ref:`codecommit <cli:aws codecommit>` ]

.. _cli:aws codecommit get-commit:


**********
get-commit
**********



===========
Description
===========



Returns information about a commit, including commit message and committer information.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codecommit-2015-04-13/GetCommit>`_


========
Synopsis
========

::

    get-commit
  --repository-name <value>
  --commit-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--repository-name`` (string)


  The name of the repository to which the commit was made.

  

``--commit-id`` (string)


  The commit ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

commit -> (structure)

  

  A commit data type object that contains information about the specified commit.

  

  treeId -> (string)

    

    Tree information for the specified commit.

    

    

  parents -> (list)

    

    The parent list for the specified commit.

    

    (string)

      

      

    

  message -> (string)

    

    The commit message associated with the specified commit.

    

    

  author -> (structure)

    

    Information about the author of the specified commit. Information includes the date in timestamp format with GMT offset, the name of the author, and the email address for the author, as configured in Git.

    

    name -> (string)

      

      The name of the user who made the specified commit.

      

      

    email -> (string)

      

      The email address associated with the user who made the commit, if any.

      

      

    date -> (string)

      

      The date when the specified commit was pushed to the repository.

      

      

    

  committer -> (structure)

    

    Information about the person who committed the specified commit, also known as the committer. Information includes the date in timestamp format with GMT offset, the name of the committer, and the email address for the committer, as configured in Git.

     

    For more information about the difference between an author and a committer in Git, see `Viewing the Commit History <http://git-scm.com/book/ch2-3.html>`_ in Pro Git by Scott Chacon and Ben Straub.

    

    name -> (string)

      

      The name of the user who made the specified commit.

      

      

    email -> (string)

      

      The email address associated with the user who made the commit, if any.

      

      

    date -> (string)

      

      The date when the specified commit was pushed to the repository.

      

      

    

  additionalData -> (string)

    

    Any additional data associated with the specified commit.

    

    

  

