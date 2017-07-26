[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses set-identity-dkim-enabled:


*************************
set-identity-dkim-enabled
*************************



===========
Description
===========



Enables or disables Easy DKIM signing of email sent from an identity:

 

 
* If Easy DKIM signing is enabled for a domain name identity (e.g., ``example.com`` ), then Amazon SES will DKIM-sign all email sent by addresses under that domain name (e.g., ``user@example.com`` ). 
 
* If Easy DKIM signing is enabled for an email address, then Amazon SES will DKIM-sign all email sent by that email address. 
 

 

For email addresses (e.g., ``user@example.com`` ), you can only enable Easy DKIM signing if the corresponding domain (e.g., ``example.com`` ) has been set up for Easy DKIM using the AWS Console or the ``verify-domain-dkim`` action.

 

This action is throttled at one request per second.

 

For more information about Easy DKIM signing, go to the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/easy-dkim.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/email-2010-12-01/SetIdentityDkimEnabled>`_


========
Synopsis
========

::

    set-identity-dkim-enabled
  --identity <value>
  --dkim-enabled | --no-dkim-enabled
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--identity`` (string)


  The identity for which DKIM signing should be enabled or disabled.

  

``--dkim-enabled`` | ``--no-dkim-enabled`` (boolean)


  Sets whether DKIM signing is enabled for an identity. Set to ``true`` to enable DKIM signing for this identity; ``false`` to disable it. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To enable or disable Easy DKIM for an Amazon SES verified identity**

The following example uses the ``set-identity-dkim-enabled`` command to disable DKIM for a verified email address::

    aws ses set-identity-dkim-enabled --identity user@example.com --no-dkim-enabled

For more information about Easy DKIM, see `Easy DKIM in Amazon SES`_ in the *Amazon Simple Email Service Developer Guide*.

.. _`Easy DKIM in Amazon SES`: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/easy-dkim.html



======
Output
======

