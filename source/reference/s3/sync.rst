[ :ref:`aws <cli:aws>` . :ref:`s3 <cli:aws s3>` ]

.. _cli:aws s3 sync:


****
sync
****



===========
Description
===========

Syncs directories and S3 prefixes. Recursively copies new and updated files from the source directory to the destination. Only creates folders in the destination if they contain one or more files.



========
Synopsis
========

::

    sync
  <LocalPath> <S3Uri> or <S3Uri> <LocalPath> or <S3Uri> <S3Uri>
  [--dryrun]
  [--quiet]
  [--include <value>]
  [--exclude <value>]
  [--acl <value>]
  [--follow-symlinks | --no-follow-symlinks]
  [--no-guess-mime-type]
  [--sse <value>]
  [--sse-c <value>]
  [--sse-c-key <value>]
  [--sse-kms-key-id <value>]
  [--sse-c-copy-source <value>]
  [--sse-c-copy-source-key <value>]
  [--storage-class <value>]
  [--grants <value> [<value>...]]
  [--website-redirect <value>]
  [--content-type <value>]
  [--cache-control <value>]
  [--content-disposition <value>]
  [--content-encoding <value>]
  [--content-language <value>]
  [--expires <value>]
  [--source-region <value>]
  [--only-show-errors]
  [--page-size <value>]
  [--ignore-glacier-warnings]
  [--metadata <value>]
  [--metadata-directive <value>]
  [--size-only]
  [--exact-timestamps]
  [--delete]




=======
Options
=======

``paths`` (string)


``--dryrun`` (boolean)
Displays the operations that would be performed using the specified command without actually running them.

``--quiet`` (boolean)
Does not display the operations performed from the specified command.

``--include`` (string)
Don't exclude files or objects in the command that match the specified pattern. See `Use of Exclude and Include Filters`_ for details.

``--exclude`` (string)
Exclude all files or objects from the command that matches the specified pattern.

``--acl`` (string)
Sets the ACL for the object when the command is performed. If you use this parameter you must have the "s3:PutObjectAcl" permission included in the list of actions for your IAM policy. Only accepts values of ``private``, ``public-read``, ``public-read-write``, ``authenticated-read``, ``aws-exec-read``, ``bucket-owner-read``, ``bucket-owner-full-control`` and ``log-delivery-write``. See `Canned ACL`_ for details

``--follow-symlinks`` | ``--no-follow-symlinks`` (boolean)
Symbolic links are followed only when uploading to S3 from the local filesystem. Note that S3 does not support symbolic links, so the contents of the link target are uploaded under the name of the link. When neither ``--follow-symlinks`` nor ``--no-follow-symlinks`` is specifed, the default is to follow symlinks.

``--no-guess-mime-type`` (boolean)
Do not try to guess the mime type for uploaded files. By default the mime type of a file is guessed when it is uploaded.

``--sse`` (string)
Specifies server-side encryption of the object in S3. Valid values are ``AES256`` and ``aws:kms``. If the parameter is specified but no value is provided, ``AES256`` is used.

``--sse-c`` (string)
Specifies server-side encryption using customer provided keys of the the object in S3. ``AES256`` is the only valid value. If the parameter is specified but no value is provided, ``AES256`` is used. If you provide this value, ``--sse-c-key`` be specfied as well.

``--sse-c-key`` (string)
The customer-provided encryption key to use to server-side encrypt the object in S3. If you provide this value, ``--sse-c`` be specfied as well. The key provided should **not** be base64 encoded.

``--sse-kms-key-id`` (string)
The AWS KMS key ID that should be used to server-side encrypt the object in S3. Note that you should only provide this parameter if KMS key ID is different the default S3 master KMS key.

``--sse-c-copy-source`` (string)
This parameter should only be specified when copying an S3 object that was encrypted server-side with a customer-provided key. It specifies the algorithm to use when decrypting the source object. ``AES256`` is the only valid value. If the parameter is specified but no value is provided, ``AES256`` is used. If you provide this value, ``--sse-c-copy-source-key`` be specfied as well. 

``--sse-c-copy-source-key`` (string)
This parameter should only be specified when copying an S3 object that was encrypted server-side with a customer-provided key. Specifies the customer-provided encryption key for Amazon S3 to use to decrypt the source object. The encryption key provided must be one that was used when the source object was created. If you provide this value, ``--sse-c-copy-source`` be specfied as well. The key provided should **not** be base64 encoded.

``--storage-class`` (string)
The type of storage to use for the object. Valid choices are: STANDARD | REDUCED_REDUNDANCY | STANDARD_IA. Defaults to 'STANDARD'

``--grants`` (string)


``--website-redirect`` (string)


``--content-type`` (string)


``--cache-control`` (string)


``--content-disposition`` (string)


``--content-encoding`` (string)


``--content-language`` (string)


``--expires`` (string)


``--source-region`` (string)


``--only-show-errors`` (boolean)


``--page-size`` (integer)


``--ignore-glacier-warnings`` (boolean)


``--metadata`` (map)




Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--metadata-directive`` (string)


``--size-only`` (boolean)


``--exact-timestamps`` (boolean)


``--delete`` (boolean)




========
Examples
========

The following ``sync`` command syncs objects under a specified prefix and bucket to files in a local directory by
uploading the local files to s3.  A local file will require uploading if the size of the local file is different than
the size of the s3 object, the last modified time of the local file is newer than the last modified time of the s3
object, or the local file does not exist under the specified bucket and prefix.  In this example, the user syncs the
bucket ``mybucket`` to the local current directory.  The local current directory contains the files ``test.txt`` and
``test2.txt``.  The bucket ``mybucket`` contains no objects::

    aws s3 sync . s3://mybucket

Output::

    upload: test.txt to s3://mybucket/test.txt
    upload: test2.txt to s3://mybucket/test2.txt

The following ``sync`` command syncs objects under a specified prefix and bucket to objects under another specified
prefix and bucket by copying s3 objects.  A s3 object will require copying if the sizes of the two s3 objects differ,
the last modified time of the source is newer than the last modified time of the destination, or the s3 object does not
exist under the specified bucket and prefix destination.  In this example, the user syncs the bucket ``mybucket2`` to
the bucket ``mybucket``.  The bucket ``mybucket`` contains the objects ``test.txt`` and ``test2.txt``.  The bucket
``mybucket2`` contains no objects::

    aws s3 sync s3://mybucket s3://mybucket2

Output::

    copy: s3://mybucket/test.txt to s3://mybucket2/test.txt
    copy: s3://mybucket/test2.txt to s3://mybucket2/test2.txt

The following ``sync`` command syncs files in a local directory to objects under a specified prefix and bucket by
downloading s3 objects.  A s3 object will require downloading if the size of the s3 object differs from the size of the
local file, the last modified time of the s3 object is older than the last modified time of the local file, or the s3
object does not exist in the local directory.  Take note that when objects are downloaded from s3, the last modified
time of the local file is changed to the last modified time of the s3 object.  In this example, the user syncs the
current local directory to the bucket ``mybucket``.  The bucket ``mybucket`` contains the objects ``test.txt`` and
``test2.txt``.  The current local directory has no files::

    aws s3 sync s3://mybucket .

Output::

    download: s3://mybucket/test.txt to test.txt
    download: s3://mybucket/test2.txt to test2.txt

The following ``sync`` command syncs objects under a specified prefix and bucket to files in a local directory by
uploading the local files to s3.  Because the ``--delete`` parameter flag is thrown, any files existing under the
specified prefix and bucket but not existing in the local directory will be deleted.  In this example, the user syncs
the bucket ``mybucket`` to the local current directory.  The local current directory contains the files ``test.txt`` and
``test2.txt``.  The bucket ``mybucket`` contains the object ``test3.txt``::

    aws s3 sync . s3://mybucket --delete

Output::

    upload: test.txt to s3://mybucket/test.txt
    upload: test2.txt to s3://mybucket/test2.txt
    delete: s3://mybucket/test3.txt

The following ``sync`` command syncs objects under a specified prefix and bucket to files in a local directory by
uploading the local files to s3.  Because the ``--exclude`` parameter flag is thrown, all files matching the pattern
existing both in s3 and locally will be excluded from the sync.  In this example, the user syncs the bucket ``mybucket``
to the local current directory.  The local current directory contains the files ``test.jpg`` and ``test2.txt``.  The
bucket ``mybucket`` contains the object ``test.jpg`` of a different size than the local ``test.jpg``::

    aws s3 sync . s3://mybucket --exclude "*.jpg"

Output::

    upload: test2.txt to s3://mybucket/test2.txt

The following ``sync`` command syncs files under a local directory to objects under a specified prefix and bucket by
downloading s3 objects.  This example uses the ``--exclude`` parameter flag to exclude a specified directory
and s3 prefix from the ``sync`` command.  In this example, the user syncs the local current directory to the bucket
``mybucket``.  The local current directory contains the files ``test.txt`` and ``another/test2.txt``.  The bucket
``mybucket`` contains the objects ``another/test5.txt`` and ``test1.txt``::

    aws s3 sync s3://mybucket/ . --exclude "*another/*"

Output::

    download: s3://mybucket/test1.txt to test1.txt

The following ``sync`` command syncs files between two buckets in different regions::

    aws s3 sync s3://my-us-west-2-bucket s3://my-us-east-1-bucket --source-region us-west-2 --region us-east-1

.. _Use of Exclude and Include Filters: http://docs.aws.amazon.com/cli/latest/reference/s3/index.html#use-of-exclude-and-include-filters
.. _Canned ACL: http://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl
