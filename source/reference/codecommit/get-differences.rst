[ :ref:`aws <cli:aws>` . :ref:`codecommit <cli:aws codecommit>` ]

.. _cli:aws codecommit get-differences:


***************
get-differences
***************



===========
Description
===========



Returns information about the differences in a valid commit specifier (such as a branch, tag, HEAD, commit ID or other fully qualified reference). Results can be limited to a specified path.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codecommit-2015-04-13/GetDifferences>`_


========
Synopsis
========

::

    get-differences
  --repository-name <value>
  [--before-commit-specifier <value>]
  --after-commit-specifier <value>
  [--before-path <value>]
  [--after-path <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--repository-name`` (string)


  The name of the repository where you want to get differences.

  

``--before-commit-specifier`` (string)


  The branch, tag, HEAD, or other fully qualified reference used to identify a commit. For example, the full commit ID. Optional. If not specified, all changes prior to the ``afterCommitSpecifier`` value will be shown. If you do not use ``beforeCommitSpecifier`` in your request, consider limiting the results with ``maxResults`` .

  

``--after-commit-specifier`` (string)


  The branch, tag, HEAD, or other fully qualified reference used to identify a commit.

  

``--before-path`` (string)


  The file path in which to check for differences. Limits the results to this path. Can also be used to specify the previous name of a directory or folder. If ``beforePath`` and ``afterPath`` are not specified, differences will be shown for all paths.

  

``--after-path`` (string)


  The file path in which to check differences. Limits the results to this path. Can also be used to specify the changed name of a directory or folder, if it has changed. If not specified, differences will be shown for all paths.

  

``--max-results`` (integer)


  A non-negative integer used to limit the number of returned results.

  

``--next-token`` (string)


  An enumeration token that when provided in a request, returns the next batch of the results.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

differences -> (list)

  

  A differences data type object that contains information about the differences, including whether the difference is added, modified, or deleted (A, D, M).

  

  (structure)

    

    Returns information about a set of differences for a commit specifier.

    

    beforeBlob -> (structure)

      

      Information about a ``beforeBlob`` data type object, including the ID, the file mode permission code, and the path.

      

      blobId -> (string)

        

        The full ID of the blob.

        

        

      path -> (string)

        

        The path to the blob and any associated file name, if any.

        

        

      mode -> (string)

        

        The file mode permissions of the blob. File mode permission codes include:

         

         
        * ``100644`` indicates read/write 
         
        * ``100755`` indicates read/write/execute 
         
        * ``160000`` indicates a submodule 
         
        * ``120000`` indicates a symlink 
         

        

        

      

    afterBlob -> (structure)

      

      Information about an ``afterBlob`` data type object, including the ID, the file mode permission code, and the path.

      

      blobId -> (string)

        

        The full ID of the blob.

        

        

      path -> (string)

        

        The path to the blob and any associated file name, if any.

        

        

      mode -> (string)

        

        The file mode permissions of the blob. File mode permission codes include:

         

         
        * ``100644`` indicates read/write 
         
        * ``100755`` indicates read/write/execute 
         
        * ``160000`` indicates a submodule 
         
        * ``120000`` indicates a symlink 
         

        

        

      

    changeType -> (string)

      

      Whether the change type of the difference is an addition (A), deletion (D), or modification (M).

      

      

    

  

NextToken -> (string)

  

  An enumeration token that can be used in a request to return the next batch of the results.

  

  

