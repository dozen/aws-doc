[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses get-identity-dkim-attributes:


****************************
get-identity-dkim-attributes
****************************



===========
Description
===========



Returns the current status of Easy DKIM signing for an entity. For domain name identities, this action also returns the DKIM tokens that are required for Easy DKIM signing, and whether Amazon SES has successfully verified that these tokens have been published.

 

This action takes a list of identities as input and returns the following information for each:

 

 
* Whether Easy DKIM signing is enabled or disabled.
 
* A set of DKIM tokens that represent the identity. If the identity is an email address, the tokens represent the domain of that address.
 
* Whether Amazon SES has successfully verified the DKIM tokens published in the domain's DNS. This information is only returned for domain name identities, not for email addresses.
 

 

This action is throttled at one request per second and can only get DKIM attributes for up to 100 identities at a time.

 

For more information about creating DNS records using DKIM tokens, go to the `Amazon SES Developer Guide`_ .



========
Synopsis
========

::

    get-identity-dkim-attributes
  --identities <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--identities`` (list)


  A list of one or more verified identities - email addresses, domains, or both.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get the Amazon SES Easy DKIM attributes for a list of identities**

The following example uses the ``get-identity-dkim-attributes`` command to retrieve the Amazon SES Easy DKIM attributes for a list of identities::

    aws ses get-identity-dkim-attributes --identities "example.com" "user@example.com"

Output::

 {
    "DkimAttributes": {
        "example.com": {
            "DkimTokens": [
                "EXAMPLEjcs5xoyqytjsotsijas7236gr",
                "EXAMPLEjr76cvoc6mysspnioorxsn6ep",
                "EXAMPLEkbmkqkhlm2lyz77ppkulerm4k"
            ],
            "DkimEnabled": true,
            "DkimVerificationStatus": "Success"
        },
        "user@example.com": {
            "DkimEnabled": false,
            "DkimVerificationStatus": "NotStarted"
        }
    }
 }

If you call this command with an identity that you have never submitted for verification, that identity won't appear in the output.

For more information about Easy DKIM, see `Easy DKIM in Amazon SES`_ in the *Amazon Simple Email Service Developer Guide*.

.. _`Easy DKIM in Amazon SES`: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/easy-dkim.html


======
Output
======

DkimAttributes -> (map)

  

  The DKIM attributes for an email address or a domain. 

  

  key -> (string)

    

    

  value -> (structure)

    

    Represents the DKIM attributes of a verified email address or a domain.

    

    DkimEnabled -> (boolean)

      

      True if DKIM signing is enabled for email sent from the identity; false otherwise.

      

      

    DkimVerificationStatus -> (string)

      

      Describes whether Amazon SES has successfully verified the DKIM DNS records (tokens) published in the domain name's DNS. (This only applies to domain identities, not email address identities.)

      

      

    DkimTokens -> (list)

      

      A set of character strings that represent the domain's identity. Using these tokens, you will need to create DNS CNAME records that point to DKIM public keys hosted by Amazon SES. Amazon Web Services will eventually detect that you have updated your DNS records; this detection process may take up to 72 hours. Upon successful detection, Amazon SES will be able to DKIM-sign email originating from that domain. (This only applies to domain identities, not email address identities.)

       

      For more information about creating DNS records using DKIM tokens, go to the `Amazon SES Developer Guide`_ .

      

      (string)

        

        

      

    

  



.. _Amazon SES Developer Guide: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/easy-dkim-dns-records.html
