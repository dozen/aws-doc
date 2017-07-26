[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway delete-base-path-mapping:


************************
delete-base-path-mapping
************************



===========
Description
===========



Deletes the  BasePathMapping resource.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/DeleteBasePathMapping>`_


========
Synopsis
========

::

    delete-base-path-mapping
  --domain-name <value>
  --base-path <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  The domain name of the  BasePathMapping resource to delete.

  

``--base-path`` (string)


  The base path name of the  BasePathMapping resource to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a base path mapping for a custom domain name**

Command::

  aws apigateway delete-base-path-mapping --domain-name 'api.domain.tld' --base-path 'dev'


======
Output
======

None