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

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudtrail-2013-11-01/ListPublicKeys>`_


========
Synopsis
========

::

    list-public-keys
  [--start-time <value>]
  [--end-time <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list all public keys for a trail**

The following ``list-public-keys`` command returns all public keys whose private keys were used to sign the digest files within the specified time range::

  aws cloudtrail list-public-keys --start-time 2016-01-01T20:30:00.000Z

Output::

  {
    "PublicKeyList": [
        {
           "ValidityStartTime": 1453076702.0, 
           "ValidityEndTime": 1455668702.0, 
           "Value": "MIIBCgKCAQEAlSS3cl92HDycr/MTj0moOhas8habjrraXw+KzlWF0axSI2tcF+3iJ9BKQAVSKxGwxwu3m0wG3J+kUl1xboEcEPHYoIYMbgfSw7KGnuDKwkLzsQWhUJ0cIbOHASox1vv/5fNXkrHhGbDCHeVXm804c83nvHUEFYThr1PfyP/8HwrCtR3FX5OANtQCP61C1nJtSSkC8JSQUOrIP4CuwJjc+4WGDk+BGH5m9iuiAKkipEHWmUl8/P7XpfpWQuk4h8g3pXZOrNXr08lbh4d39svj7UqdhvOXoBISp9t/EXYuePGEtBdrKD9Dz+VHwyUPtBQvYr9BnkF88qBnaPNhS44rzwIDAQAB", 
           "Fingerprint": "7f3f401420072e50a65a141430817ab3"
       }
    ]
  }

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

  

  

