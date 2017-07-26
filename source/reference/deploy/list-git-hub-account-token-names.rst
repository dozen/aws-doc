[ :ref:`aws <cli:aws>` . :ref:`deploy <cli:aws deploy>` ]

.. _cli:aws deploy list-git-hub-account-token-names:


********************************
list-git-hub-account-token-names
********************************



===========
Description
===========



Lists the names of stored connections to GitHub accounts.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codedeploy-2014-10-06/ListGitHubAccountTokenNames>`_


========
Synopsis
========

::

    list-git-hub-account-token-names
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--next-token`` (string)


  An identifier returned from the previous list-git-hub-account-token-names call. It can be used to return the next set of names in the list. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

tokenNameList -> (list)

  

  A list of names of connections to GitHub accounts.

  

  (string)

    

    

  

nextToken -> (string)

  

  If a large amount of information is returned, an identifier is also returned. It can be used in a subsequent list-git-hub-account-token-names call to return the next set of names in the list. 

  

  

