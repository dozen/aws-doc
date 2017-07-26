[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses delete-identity:


***************
delete-identity
***************



===========
Description
===========



Deletes the specified identity (email address or domain) from the list of verified identities.

 

This action is throttled at one request per second.



========
Synopsis
========

::

    delete-identity
  --identity <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--identity`` (string)


  The identity to be removed from the list of identities for the AWS Account.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete an identity**

The following example uses the ``delete-identity`` command to delete an identity from the list of identities verified with Amazon SES::

    aws ses delete-identity --identity user@example.com

For more information about verified identities, see `Verifying Email Addresses and Domains in Amazon SES`_ in the *Amazon Simple Email Service Developer Guide*.

.. _`Verifying Email Addresses and Domains in Amazon SES`: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/verify-addresses-and-domains.html


======
Output
======

