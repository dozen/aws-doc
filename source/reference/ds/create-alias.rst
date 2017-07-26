[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds create-alias:


************
create-alias
************



===========
Description
===========



Creates an alias for a directory and assigns the alias to the directory. The alias is used to construct the access URL for the directory, such as ``http://alias.awsapps.com`` .

 

.. warning::

   

  After an alias has been created, it cannot be deleted or reused, so this operation should only be used when absolutely necessary.

   



========
Synopsis
========

::

    create-alias
  --directory-id <value>
  --alias <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--directory-id`` (string)


  The identifier of the directory for which to create the alias.

  

``--alias`` (string)


  The requested alias.

   

  The alias must be unique amongst all aliases in AWS. This operation throws an ``EntityAlreadyExistsException`` error if the alias already exists.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

DirectoryId -> (string)

  

  The identifier of the directory.

  

  

Alias -> (string)

  

  The alias for the directory.

  

  

