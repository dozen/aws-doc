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

  



========
Synopsis
========

::

    update-repository-description
  --repository-name <value>
  [--repository-description <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--repository-name`` (string)


  The name of the repository to set or change the comment or description for.

  

``--repository-description`` (string)


  The new comment or description for the specified repository.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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