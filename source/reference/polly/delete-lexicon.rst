[ :ref:`aws <cli:aws>` . :ref:`polly <cli:aws polly>` ]

.. _cli:aws polly delete-lexicon:


**************
delete-lexicon
**************



===========
Description
===========



Deletes the specified pronunciation lexicon stored in an AWS Region. A lexicon which has been deleted is not available for speech synthesis, nor is it possible to retrieve it using either the ``get-lexicon`` or ``ListLexicon`` APIs.

 

For more information, see `Managing Lexicons <http://docs.aws.amazon.com/polly/latest/dg/managing-lexicons.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/polly-2016-06-10/DeleteLexicon>`_


========
Synopsis
========

::

    delete-lexicon
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the lexicon to delete. Must be an existing lexicon in the region.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

