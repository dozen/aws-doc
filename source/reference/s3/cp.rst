[ :ref:`aws <cli:aws>` . :ref:`s3 <cli:aws s3>` ]

.. _cli:aws s3 cp:


**
cp
**



===========
Description
===========

Copies a local file or S3 object to another location locally or in S3.



========
Synopsis
========

::

    cp
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
  [--expected-size <value>]
  [--recursive]




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


``--expected-size`` (string)


``--recursive`` (boolean)




========
Examples
========

**Copying a local file to S3**

The following ``cp`` command copies a single file to a specified
bucket and key::

    aws s3 cp test.txt s3://mybucket/test2.txt

Output::

    upload: test.txt to s3://mybucket/test2.txt


**Copying a file from S3 to S3**

The following ``cp`` command copies a single s3 object to a specified bucket and key::

    aws s3 cp s3://mybucket/test.txt s3://mybucket/test2.txt

Output::

    copy: s3://mybucket/test.txt to s3://mybucket/test2.txt


**Copying an S3 object to a local file**

The following ``cp`` command copies a single object to a specified file locally::

    aws s3 cp s3://mybucket/test.txt test2.txt

Output::

    download: s3://mybucket/test.txt to test2.txt


**Copying an S3 object from one bucket to another**

The following ``cp`` command copies a single object to a specified bucket while retaining its original name::

    aws s3 cp s3://mybucket/test.txt s3://mybucket2/

Output::

    copy: s3://mybucket/test.txt to s3://mybucket2/test.txt

**Recursively copying S3 objects to a local directory**

When passed with the parameter ``--recursive``, the following ``cp`` command recursively copies all objects under a
specified prefix and bucket to a specified directory.  In this example, the bucket ``mybucket`` has the objects
``test1.txt`` and ``test2.txt``::

    aws s3 cp s3://mybucket . --recursive

Output::

    download: s3://mybucket/test1.txt to test1.txt
    download: s3://mybucket/test2.txt to test2.txt

**Recursively copying local files to S3**

When passed with the parameter ``--recursive``, the following ``cp`` command recursively copies all files under a
specifed directory to a specified bucket and prefix while excluding some files by using an ``--exclude`` parameter.  In
this example, the directory ``myDir`` has the files ``test1.txt`` and ``test2.jpg``::

    aws s3 cp myDir s3://mybucket/ --recursive --exclude "*.jpg"

Output::

    upload: myDir/test1.txt to s3://mybucket2/test1.txt

**Recursively copying S3 objects to another bucket**

When passed with the parameter ``--recursive``, the following ``cp`` command recursively copies all objects under a
specifed bucket to another bucket while excluding some objects by using an ``--exclude`` parameter.  In this example,
the bucket ``mybucket`` has the objects ``test1.txt`` and ``another/test1.txt``::

    aws s3 cp s3://mybucket/ s3://mybucket2/ --recursive --exclude "mybucket/another/*"

Output::

    copy: s3://mybucket/test1.txt to s3://mybucket2/test1.txt

You can combine ``--exclude`` and ``--include`` options to copy only objects that match a pattern, excluding all others::

    aws s3 cp s3://mybucket/logs/ s3://mybucket2/logs/ --recursive --exclude "*" --include "*.log" 

Output::

    copy: s3://mybucket/test/test.log to s3://mybucket2/test/test.log
    copy: s3://mybucket/test3.log to s3://mybucket2/test3.log

**Setting the Access Control List (ACL) while copying an S3 object**

The following ``cp`` command copies a single object to a specified bucket and key while setting the ACL to
``public-read-write``::

    aws s3 cp s3://mybucket/test.txt s3://mybucket/test2.txt --acl public-read-write

Output::

    copy: s3://mybucket/test.txt to s3://mybucket/test2.txt

Note that if you're using the ``--acl`` option, ensure that any associated IAM
policies include the ``"s3:PutObjectAcl"`` action::

    aws iam get-user-policy --user-name myuser --policy-name mypolicy

Output::

    {
        "UserName": "myuser",
        "PolicyName": "mypolicy",
        "PolicyDocument": {
            "Version": "2012-10-17",
            "Statement": [
                {
                    "Action": [
                        "s3:PutObject",
                        "s3:PutObjectAcl"
                    ],
                    "Resource": [
                        "arn:aws:s3:::mybucket/*"
                    ],
                    "Effect": "Allow",
                    "Sid": "Stmt1234567891234"
                }
            ]
        }
    }

**Granting permissions for an S3 object**

The following ``cp`` command illustrates the use of the ``--grants`` option to grant read access to all users and full
control to a specific user identified by their email address::

  aws s3 cp file.txt s3://mybucket/ --grants read=uri=http://acs.amazonaws.com/groups/global/AllUsers full=emailaddress=user@example.com

Output::

    upload: file.txt to s3://mybucket/file.txt

**Uploading a local file stream to S3**

The following ``cp`` command uploads a local file stream from standard input to a specified bucket and key::

    aws s3 cp - s3://mybucket/stream.txt


**Downloading a S3 object as a local file stream**

The following ``cp`` command downloads a S3 object locally as a stream to standard output::

    aws s3 cp s3://mybucket/stream.txt -


.. _Use of Exclude and Include Filters: http://docs.aws.amazon.com/cli/latest/reference/s3/index.html#use-of-exclude-and-include-filters
.. _Canned ACL: http://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl
