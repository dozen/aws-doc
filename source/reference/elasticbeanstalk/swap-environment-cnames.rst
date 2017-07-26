[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk swap-environment-cnames:


***********************
swap-environment-cnames
***********************



===========
Description
===========



Swaps the CNAMEs of two environments.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/SwapEnvironmentCNAMEs>`_


========
Synopsis
========

::

    swap-environment-cnames
  [--source-environment-id <value>]
  [--source-environment-name <value>]
  [--destination-environment-id <value>]
  [--destination-environment-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--source-environment-id`` (string)


  The ID of the source environment.

   

  Condition: You must specify at least the ``SourceEnvironmentID`` or the ``SourceEnvironmentName`` . You may also specify both. If you specify the ``SourceEnvironmentId`` , you must specify the ``DestinationEnvironmentId`` . 

  

``--source-environment-name`` (string)


  The name of the source environment.

   

  Condition: You must specify at least the ``SourceEnvironmentID`` or the ``SourceEnvironmentName`` . You may also specify both. If you specify the ``SourceEnvironmentName`` , you must specify the ``DestinationEnvironmentName`` . 

  

``--destination-environment-id`` (string)


  The ID of the destination environment.

   

  Condition: You must specify at least the ``DestinationEnvironmentID`` or the ``DestinationEnvironmentName`` . You may also specify both. You must specify the ``SourceEnvironmentId`` with the ``DestinationEnvironmentId`` . 

  

``--destination-environment-name`` (string)


  The name of the destination environment.

   

  Condition: You must specify at least the ``DestinationEnvironmentID`` or the ``DestinationEnvironmentName`` . You may also specify both. You must specify the ``SourceEnvironmentName`` with the ``DestinationEnvironmentName`` . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To swap environment CNAMES**

The following command swaps the assigned subdomains of two environments::

  aws elasticbeanstalk swap-environment-cnames --source-environment-name my-env-blue --destination-environment-name my-env-green


======
Output
======

None