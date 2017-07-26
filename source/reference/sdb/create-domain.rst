[ :ref:`aws <cli:aws>` . :ref:`sdb <cli:aws sdb>` ]

.. _cli:aws sdb create-domain:


*************
create-domain
*************



===========
Description
===========



The ``create-domain`` operation creates a new domain. The domain name should be unique among the domains associated with the Access Key ID provided in the request. The ``create-domain`` operation may take 10 or more seconds to complete. 

 

The client can create up to 100 domains per account. 

 

If the client requires additional domains, go to `http\://aws.amazon.com/contact-us/simpledb-limit-request/`_ . 



.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.sdb true`` 



========
Synopsis
========

::

    create-domain
  --domain-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-name`` (string)
The name of the domain to create. The name can range between 3 and 255 characters and can contain the following characters: a-z, A-Z, 0-9, '_', '-', and '.'.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None

.. _http\://aws.amazon.com/contact-us/simpledb-limit-request/: http://aws.amazon.com/contact-us/simpledb-limit-request/
