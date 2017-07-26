[ :ref:`aws <cli:aws>` . :ref:`discovery <cli:aws discovery>` ]

.. _cli:aws discovery create-application:


******************
create-application
******************



===========
Description
===========



Creates an application with the given name and description.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/discovery-2015-11-01/CreateApplication>`_


========
Synopsis
========

::

    create-application
  --name <value>
  [--description <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  Name of the application to be created.

  

``--description`` (string)


  Description of the application to be created.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

configurationId -> (string)

  

  Configuration ID of an application to be created.

  

  

