[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses get-identity-verification-attributes:


************************************
get-identity-verification-attributes
************************************



===========
Description
===========



Given a list of identities (email addresses and/or domains), returns the verification status and (for domain identities) the verification token for each identity.

 

This action is throttled at one request per second and can only get verification attributes for up to 100 identities at a time.



========
Synopsis
========

::

    get-identity-verification-attributes
  --identities <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--identities`` (list)


  A list of identities.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get the Amazon SES verification status for a list of identities**

The following example uses the ``get-identity-verification-attributes`` command to retrieve the Amazon SES verification status for a list of identities::

    aws ses get-identity-verification-attributes --identities "user1@example.com" "user2@example.com"

Output::

 {
    "VerificationAttributes": {
        "user1@example.com": {
            "VerificationStatus": "Success"
        },
        "user2@example.com": {
            "VerificationStatus": "Pending"
        }
    }
 }

If you call this command with an identity that you have never submitted for verification, that identity won't appear in the output.

For more information about verified identities, see `Verifying Email Addresses and Domains in Amazon SES`_ in the *Amazon Simple Email Service Developer Guide*.

.. _`Verifying Email Addresses and Domains in Amazon SES`: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/verify-addresses-and-domains.html


======
Output
======

VerificationAttributes -> (map)

  

  A map of Identities to IdentityVerificationAttributes objects.

  

  key -> (string)

    

    

  value -> (structure)

    

    Represents the verification attributes of a single identity.

    

    VerificationStatus -> (string)

      

      The verification status of the identity: "Pending", "Success", "Failed", or "TemporaryFailure".

      

      

    VerificationToken -> (string)

      

      The verification token for a domain identity. Null for email address identities.

      

      

    

  

