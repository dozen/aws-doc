[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses create-configuration-set:


************************
create-configuration-set
************************



===========
Description
===========



Creates a configuration set.

 

Configuration sets enable you to publish email sending events. For information about using configuration sets, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/monitor-sending-activity.html>`_ .

 

This action is throttled at one request per second.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/email-2010-12-01/CreateConfigurationSet>`_


========
Synopsis
========

::

    create-configuration-set
  --configuration-set <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--configuration-set`` (structure)


  A data structure that contains the name of the configuration set.

  



Shorthand Syntax::

    Name=string




JSON Syntax::

  {
    "Name": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

