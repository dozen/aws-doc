[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses verify-domain-dkim:


******************
verify-domain-dkim
******************



===========
Description
===========



Returns a set of DKIM tokens for a domain. DKIM *tokens* are character strings that represent your domain's identity. Using these tokens, you will need to create DNS CNAME records that point to DKIM public keys hosted by Amazon SES. Amazon Web Services will eventually detect that you have updated your DNS records; this detection process may take up to 72 hours. Upon successful detection, Amazon SES will be able to DKIM-sign email originating from that domain.

 

This action is throttled at one request per second.

 

To enable or disable Easy DKIM signing for a domain, use the ``set-identity-dkim-enabled`` action.

 

For more information about creating DNS records using DKIM tokens, go to the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/easy-dkim-dns-records.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/email-2010-12-01/VerifyDomainDkim>`_


========
Synopsis
========

::

    verify-domain-dkim
  --domain <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain`` (string)


  The name of the domain to be verified for Easy DKIM signing.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To generate a verified domain's DKIM tokens for DKIM signing with Amazon SES**

The following example uses the ``verify-domain-dkim`` command to generate DKIM tokens for a domain that has been verified with Amazon SES::

    aws ses verify-domain-dkim --domain example.com

Output::

 {
    "DkimTokens": [
        "EXAMPLEq76owjnks3lnluwg65scbemvw",
        "EXAMPLEi3dnsj67hstzaj673klariwx2",
        "EXAMPLEwfbtcukvimehexktmdtaz6naj"
    ]
 }

To set up DKIM, you must use the returned DKIM tokens to update your domain's DNS settings with CNAME records that point to DKIM public keys hosted by Amazon SES. For more information, see `Easy DKIM in Amazon SES`_ in the *Amazon Simple Email Service Developer Guide*.

.. _`Easy DKIM in Amazon SES`: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/easy-dkim.html


======
Output
======

DkimTokens -> (list)

  

  A set of character strings that represent the domain's identity. If the identity is an email address, the tokens represent the domain of that address.

   

  Using these tokens, you will need to create DNS CNAME records that point to DKIM public keys hosted by Amazon SES. Amazon Web Services will eventually detect that you have updated your DNS records; this detection process may take up to 72 hours. Upon successful detection, Amazon SES will be able to DKIM-sign emails originating from that domain.

   

  For more information about creating DNS records using DKIM tokens, go to the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/easy-dkim-dns-records.html>`_ .

  

  (string)

    

    

  

