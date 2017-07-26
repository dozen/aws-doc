[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses list-identities:


***************
list-identities
***************



===========
Description
===========



Returns a list containing all of the identities (email addresses and domains) for a specific AWS Account, regardless of verification status.

 

This action is throttled at one request per second.



``list-identities`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Identities``


========
Synopsis
========

::

    list-identities
  [--identity-type <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--identity-type`` (string)


  The type of the identities to list. Possible values are "EmailAddress" and "Domain". If this parameter is omitted, then all identities will be listed.

  

  Possible values:

  
  *   ``EmailAddress``

  
  *   ``Domain``

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``next-token`` will be provided in the output that you can use to resume pagination. This ``next-token`` response element should **not** be used directly outside of the AWS CLI.

   

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To list all identities (email addresses and domains) for a specific AWS account**


The following example uses the ``list-identities`` command to list all identities that have been submitted for verification with Amazon SES::

    aws ses list-identities

Output::

 {
     "Identities": [
       "user@example.com",
       "example.com"
     ]
 }
  

The list that is returned contains all identities regardless of verification status (verified, pending verification, failure, etc.).

In this example, email addresses *and* domains are returned because we did not specify the identity-type parameter.

For more information about verification, see `Verifying Email Addresses and Domains in Amazon SES`_ in the *Amazon Simple Email Service Developer Guide*.

.. _`Verifying Email Addresses and Domains in Amazon SES`: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/verify-addresses-and-domains.html


======
Output
======

Identities -> (list)

  

  A list of identities.

  

  (string)

    

    

  

NextToken -> (string)

  

  The token used for pagination.

  

  

