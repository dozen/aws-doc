[ :ref:`aws <cli:aws>` . :ref:`codecommit <cli:aws codecommit>` ]

.. _cli:aws codecommit update-repository-description:


*****************************
update-repository-description
*****************************



===========
Description
===========



Sets or changes the comment or description for a repository.

 

.. note::

   

  The description field for a repository accepts all HTML characters and all valid Unicode characters. Applications that do not HTML-encode the description and display it in a web page could expose users to potentially malicious code. Make sure that you HTML-encode the description field in any application that uses this API to display the repository description on a web page.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codecommit-2015-04-13/UpdateRepositoryDescription>`_


========
Synopsis
========

::

    update-repository-description
  --repository-name <value>
  [--repository-description <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--repository-name`` (string)


  The name of the repository to set or change the comment or description for.

  

``--repository-description`` (string)


  The new comment or description for the specified repository. Repository descriptions are limited to 1,000 characters.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To change the description for a repository**

This example changes the description for an AWS CodeCommit repository. This command produces output only if there are errors.

Command::

  aws codecommit update-repository-description --repository-name MyDemoRepo --repository-description "This description was changed"

Output::

  None.

======
Output
======

None