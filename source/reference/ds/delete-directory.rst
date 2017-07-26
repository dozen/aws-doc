[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds delete-directory:


****************
delete-directory
****************



===========
Description
===========



Deletes an AWS Directory Service directory.

 

Before you call *delete-directory* , ensure that all of the required permissions have been explicitly granted through a policy. For details about what permissions are required to run the *delete-directory* operation, see `AWS Directory Service API Permissions\: Actions, Resources, and Conditions Reference <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/UsingWithDS_IAM_ResourcePermissions.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ds-2015-04-16/DeleteDirectory>`_


========
Synopsis
========

::

    delete-directory
  --directory-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-id`` (string)


  The identifier of the directory to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DirectoryId -> (string)

  

  The directory identifier.

  

  

