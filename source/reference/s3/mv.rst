[ :ref:`aws <cli:aws>` . :ref:`s3 <cli:aws s3>` ]

.. _cli:aws s3 mv:


**
mv
**



===========
Description
===========

Moves a local file or S3 object to another location locally or in S3.



========
Synopsis
========

::

    mv
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
  [--force-glacier-transfer]
  [--metadata <value>]
  [--metadata-directive <value>]
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
Don't exclude files or objects in the command that match the specified pattern. See `Use of Exclude and Include Filters <http://docs.aws.amazon.com/cli/latest/reference/s3/index.html#use-of-exclude-and-include-filters>`_ for details.

``--exclude`` (string)
Exclude all files or objects from the command that matches the specified pattern.

``--acl`` (string)
Sets the ACL for the object when the command is performed. If you use this parameter you must have the "s3:PutObjectAcl" permission included in the list of actions for your IAM policy. Only accepts values of ``private``, ``public-read``, ``public-read-write``, ``authenticated-read``, ``aws-exec-read``, ``bucket-owner-read``, ``bucket-owner-full-control`` and ``log-delivery-write``. See `Canned ACL <http://docs.aws.amazon.com/AmazonS3/latest/dev/acl-overview.html#canned-acl>`_ for details

``--follow-symlinks`` | ``--no-follow-symlinks`` (boolean)
Symbolic links are followed only when uploading to S3 from the local filesystem. Note that S3 does not support symbolic links, so the contents of the link target are uploaded under the name of the link. When neither ``--follow-symlinks`` nor ``--no-follow-symlinks`` is specifed, the default is to follow symlinks.

``--no-guess-mime-type`` (boolean)
Do not try to guess the mime type for uploaded files. By default the mime type of a file is guessed when it is uploaded.

``--sse`` (string)
Specifies server-side encryption of the object in S3. Valid values are ``AES256`` and ``aws:kms``. If the parameter is specified but no value is provided, ``AES256`` is used.

``--sse-c`` (string)
Specifies server-side encryption using customer provided keys of the the object in S3. ``AES256`` is the only valid value. If the parameter is specified but no value is provided, ``AES256`` is used. If you provide this value, ``--sse-c-key`` must be specified as well.

``--sse-c-key`` (string)
The customer-provided encryption key to use to server-side encrypt the object in S3. If you provide this value, ``--sse-c`` must be specified as well. The key provided should **not** be base64 encoded.

``--sse-kms-key-id`` (string)
The AWS KMS key ID that should be used to server-side encrypt the object in S3. Note that you should only provide this parameter if KMS key ID is different the default S3 master KMS key.

``--sse-c-copy-source`` (string)
This parameter should only be specified when copying an S3 object that was encrypted server-side with a customer-provided key. It specifies the algorithm to use when decrypting the source object. ``AES256`` is the only valid value. If the parameter is specified but no value is provided, ``AES256`` is used. If you provide this value, ``--sse-c-copy-source-key`` must be specfied as well. 

``--sse-c-copy-source-key`` (string)
This parameter should only be specified when copying an S3 object that was encrypted server-side with a customer-provided key. Specifies the customer-provided encryption key for Amazon S3 to use to decrypt the source object. The encryption key provided must be one that was used when the source object was created. If you provide this value, ``--sse-c-copy-source`` be specfied as well. The key provided should **not** be base64 encoded.

``--storage-class`` (string)
The type of storage to use for the object. Valid choices are: STANDARD | REDUCED_REDUNDANCY | STANDARD_IA. Defaults to 'STANDARD'

``--grants`` (string)


  Grant specific permissions to individual users or groups. You can supply a list of grants of the form

  ::

    --grants Permission=Grantee_Type=Grantee_ID [Permission=Grantee_Type=Grantee_ID ...]

  To specify the same permission type for multiple grantees, specify the permission as such as ::

    --grants Permission=Grantee_Type=Grantee_ID,Grantee_Type=Grantee_ID,...

  Each value contains the following elements:

  
  * ``Permission`` - Specifies the granted permissions, and can be set to read, readacl, writeacl, or full.
  
  * ``Grantee_Type`` - Specifies how the grantee is to be identified, and can be set to uri, emailaddress, or id.
  
  * ``Grantee_ID`` - Specifies the grantee based on Grantee_Type. The ``Grantee_ID`` value can be one of:

    
    * **uri** - The group's URI. For more information, see `Who Is a Grantee? <http://docs.aws.amazon.com/AmazonS3/latest/dev/ACLOverview.html#SpecifyingGrantee>`_ 
    
    * **emailaddress** - The account's email address.
    
    * **id** - The account's canonical ID
    

  
  

  For more information on Amazon S3 access control, see `Access Control <http://docs.aws.amazon.com/AmazonS3/latest/dev/UsingAuthAccess.html>`_ 

``--website-redirect`` (string)
If the bucket is configured as a website, redirects requests for this object to another object in the same bucket or to an external URL. Amazon S3 stores the value of this header in the object metadata.

``--content-type`` (string)
Specify an explicit content type for this operation. This value overrides any guessed mime types.

``--cache-control`` (string)
Specifies caching behavior along the request/reply chain.

``--content-disposition`` (string)
Specifies presentational information for the object.

``--content-encoding`` (string)
Specifies what content encodings have been applied to the object and thus what decoding mechanisms must be applied to obtain the media-type referenced by the Content-Type header field.

``--content-language`` (string)
The language the content is in.

``--expires`` (string)
The date and time at which the object is no longer cacheable.

``--source-region`` (string)
When transferring objects from an s3 bucket to an s3 bucket, this specifies the region of the source bucket. Note the region specified by ``--region`` or through configuration of the CLI refers to the region of the destination bucket. If ``--source-region`` is not specified the region of the source will be the same as the region of the destination bucket.

``--only-show-errors`` (boolean)
Only errors and warnings are displayed. All other output is suppressed.

``--page-size`` (integer)
The number of results to return in each response to a list operation. The default value is 1000 (the maximum allowed). Using a lower value may help if an operation times out.

``--ignore-glacier-warnings`` (boolean)
Turns off glacier warnings. Warnings about an operation that cannot be performed because it involves copying, downloading, or moving a glacier object will no longer be printed to standard error and will no longer cause the return code of the command to be ``2``.

``--force-glacier-transfer`` (boolean)
Forces a transfer request on all Glacier objects in a sync or recursive copy.

``--metadata`` (map)
A map of metadata to store with the objects in S3. This will be applied to every object which is part of this request. In a sync, this means that files which haven't changed won't receive the new metadata. When copying between two s3 locations, the metadata-directive argument will default to 'REPLACE' unless otherwise specified.



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--metadata-directive`` (string)
Specifies whether the metadata is copied from the source object or replaced with metadata provided when copying S3 objects. Note that if the object is copied over in parts, the source object's metadata will not be copied over, no matter the value for ``--metadata-directive``, and instead the desired metadata values must be specified as parameters on the command line. Valid values are ``COPY`` and ``REPLACE``. If this parameter is not specified, ``COPY`` will be used by default. If ``REPLACE`` is used, the copied object will only have the metadata values that were specified by the CLI command. Note that if you are using any of the following parameters: ``--content-type``, ``content-language``, ``--content-encoding``, ``--content-disposition``, ``--cache-control``, or ``--expires``, you will need to specify ``--metadata-directive REPLACE`` for non-multipart copies if you want the copied objects to have the specified metadata values.

``--recursive`` (boolean)
Command is performed on all files or objects under the specified directory or prefix.



========
Examples
========

The following ``mv`` command moves a single file to a specified bucket and key::

    aws s3 mv test.txt s3://mybucket/test2.txt

Output::

    move: test.txt to s3://mybucket/test2.txt

The following ``mv`` command moves a single s3 object to a specified bucket and key::

    aws s3 mv s3://mybucket/test.txt s3://mybucket/test2.txt

Output::

    move: s3://mybucket/test.txt to s3://mybucket/test2.txt

The following ``mv`` command moves a single object to a specified file locally::

    aws s3 mv s3://mybucket/test.txt test2.txt

Output::

    move: s3://mybucket/test.txt to test2.txt

The following ``mv`` command moves a single object to a specified bucket while retaining its original name::

    aws s3 mv s3://mybucket/test.txt s3://mybucket2/

Output::

    move: s3://mybucket/test.txt to s3://mybucket2/test.txt

When passed with the parameter ``--recursive``, the following ``mv`` command recursively moves all objects under a
specified prefix and bucket to a specified directory.  In this example, the bucket ``mybucket`` has the objects
``test1.txt`` and ``test2.txt``::

    aws s3 mv s3://mybucket . --recursive

Output::

    move: s3://mybucket/test1.txt to test1.txt
    move: s3://mybucket/test2.txt to test2.txt

When passed with the parameter ``--recursive``, the following ``mv`` command recursively moves all files under a
specifed directory to a specified bucket and prefix while excluding some files by using an ``--exclude`` parameter. In
this example, the directory ``myDir`` has the files ``test1.txt`` and ``test2.jpg``::

    aws s3 mv myDir s3://mybucket/ --recursive --exclude "*.jpg"

Output::

    move: myDir/test1.txt to s3://mybucket2/test1.txt

When passed with the parameter ``--recursive``, the following ``mv`` command recursively moves all objects under a
specifed bucket to another bucket while excluding some objects by using an ``--exclude`` parameter.  In this example,
the bucket ``mybucket`` has the objects ``test1.txt`` and ``another/test1.txt``::

    aws s3 mv s3://mybucket/ s3://mybucket2/ --recursive --exclude "mybucket/another/*"

Output::

    move: s3://mybucket/test1.txt to s3://mybucket2/test1.txt

The following ``mv`` command moves a single object to a specified bucket and key while setting the ACL to
``public-read-write``::

    aws s3 mv s3://mybucket/test.txt s3://mybucket/test2.txt --acl public-read-write

Output::

    move: s3://mybucket/test.txt to s3://mybucket/test2.txt

The following ``mv`` command illustrates the use of the ``--grants`` option to grant read access to all users and full
control to a specific user identified by their email address::

  aws s3 mv file.txt s3://mybucket/ --grants read=uri=http://acs.amazonaws.com/groups/global/AllUsers full=emailaddress=user@example.com

Output::

    move: file.txt to s3://mybucket/file.txt

