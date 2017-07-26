[ :ref:`aws <cli:aws>` . :ref:`polly <cli:aws polly>` ]

.. _cli:aws polly put-lexicon:


***********
put-lexicon
***********



===========
Description
===========



Stores a pronunciation lexicon in an AWS Region. If a lexicon with the same name already exists in the region, it is overwritten by the new lexicon. Lexicon operations have eventual consistency, therefore, it might take some time before the lexicon is available to the synthesize-speech operation.

 

For more information, see `Managing Lexicons <http://docs.aws.amazon.com/polly/latest/dg/managing-lexicons.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/polly-2016-06-10/PutLexicon>`_


========
Synopsis
========

::

    put-lexicon
  --name <value>
  --content <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  Name of the lexicon. The name must follow the regular express format [0-9A-Za-z]{1,20}. That is, the name is a case-sensitive alphanumeric string up to 20 characters long. 

  

``--content`` (string)


  Content of the PLS lexicon as string data.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

