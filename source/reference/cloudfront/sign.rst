[ :ref:`aws <cli:aws>` . :ref:`cloudfront <cli:aws cloudfront>` ]

.. _cli:aws cloudfront sign:


****
sign
****



===========
Description
===========

Sign a given url.



.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.cloudfront true`` 



========
Synopsis
========

::

    sign
  --url <value>
  --key-pair-id <value>
  --private-key <value>
  --date-less-than <value>
  [--date-greater-than <value>]
  [--ip-address <value>]




=======
Options
=======

``--url`` (string)
The URL to be signed

``--key-pair-id`` (string)
The active CloudFront key pair Id for the key pair that you're using to generate the signature.

``--private-key`` (string)
file://path/to/your/private-key.pem

``--date-less-than`` (string)
The expiration date and time for the URL. Supported formats include: YYYY-MM-DD (which means 0AM UTC of that day), YYYY-MM-DDThh:mm:ss (with default timezone as UTC), YYYY-MM-DDThh:mm:ss+hh:mm or YYYY-MM-DDThh:mm:ss-hh:mm (with offset), or EpochTime (which always means UTC). Do NOT use YYYYMMDD, because it will be treated as EpochTime.

``--date-greater-than`` (string)
An optional start date and time for the URL. Supported formats include: YYYY-MM-DD (which means 0AM UTC of that day), YYYY-MM-DDThh:mm:ss (with default timezone as UTC), YYYY-MM-DDThh:mm:ss+hh:mm or YYYY-MM-DDThh:mm:ss-hh:mm (with offset), or EpochTime (which always means UTC). Do NOT use YYYYMMDD, because it will be treated as EpochTime.

``--ip-address`` (string)
An optional IP address or IP address range to allow client making the GET request from. Format: x.x.x.x/x or x.x.x.x

