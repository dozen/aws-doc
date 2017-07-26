[ :ref:`aws <cli:aws>` . :ref:`cloudtrail <cli:aws cloudtrail>` ]

.. _cli:aws cloudtrail list-public-keys:


****************
list-public-keys
****************



===========
Description
===========



Returns all public keys whose private keys were used to sign the digest files within the specified time range. The public key is needed to validate digest files that were signed with its corresponding private key.

 

.. note::

  CloudTrail uses different private/public key pairs per region. Each digest file is signed with a private key unique to its region. Therefore, when you validate a digest file from a particular region, you must look in the same region for its corresponding public key.



========
Synopsis
========

::

    list-public-keys
  [--start-time <value>]
  [--end-time <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--start-time`` (timestamp)


  Optionally specifies, in UTC, the start of the time range to look up public keys for CloudTrail digest files. If not specified, the current time is used, and the current public key is returned. 

  

``--end-time`` (timestamp)


  Optionally specifies, in UTC, the end of the time range to look up public keys for CloudTrail digest files. If not specified, the current time is used. 

  

``--next-token`` (string)


  Reserved for future use.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

PublicKeyList -> (list)

  

  Contains an array of PublicKey objects.

   

  .. note::

    The returned public keys may have validity time ranges that overlap.

  

  (structure)

    

    Contains information about a returned public key.

    

    Value -> (blob)

      

      The DER encoded public key value in PKCS#1 format.

      

      

    ValidityStartTime -> (timestamp)

      

      The starting time of validity of the public key.

      

      

    ValidityEndTime -> (timestamp)

      

      The ending time of validity of the public key.

      

      

    Fingerprint -> (string)

      

      The fingerprint of the public key.

      

      

    

  

NextToken -> (string)

  

  Reserved for future use.

  

  

