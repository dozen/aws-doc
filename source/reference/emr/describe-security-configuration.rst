[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr describe-security-configuration:


*******************************
describe-security-configuration
*******************************



===========
Description
===========



Provides the details of a security configuration by returning the configuration JSON.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticmapreduce-2009-03-31/DescribeSecurityConfiguration>`_


========
Synopsis
========

::

    describe-security-configuration
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the security configuration.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Name -> (string)

  

  The name of the security configuration.

  

  

SecurityConfiguration -> (string)

  

  The security configuration details in JSON format.

  

  

CreationDateTime -> (timestamp)

  

  The date and time the security configuration was created

  

  

