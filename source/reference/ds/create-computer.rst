[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds create-computer:


***************
create-computer
***************



===========
Description
===========



Creates a computer account in the specified directory, and joins the computer to the directory.



========
Synopsis
========

::

    create-computer
  --directory-id <value>
  --computer-name <value>
  --password <value>
  [--organizational-unit-distinguished-name <value>]
  [--computer-attributes <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--directory-id`` (string)


  The identifier of the directory in which to create the computer account.

  

``--computer-name`` (string)


  The name of the computer account.

  

``--password`` (string)


  A one-time password that is used to join the computer to the directory. You should generate a random, strong password to use for this parameter.

  

``--organizational-unit-distinguished-name`` (string)


  The fully-qualified distinguished name of the organizational unit to place the computer account in.

  

``--computer-attributes`` (list)


  An array of  Attribute objects that contain any LDAP attributes to apply to the computer account.

  



Shorthand Syntax::

    Name=string,Value=string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Value": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Computer -> (structure)

  

  A  Computer object that represents the computer account.

  

  ComputerId -> (string)

    

    The identifier of the computer.

    

    

  ComputerName -> (string)

    

    The computer name.

    

    

  ComputerAttributes -> (list)

    

    An array of  Attribute objects containing the LDAP attributes that belong to the computer account.

    

    (structure)

      

      Represents a named directory attribute.

      

      Name -> (string)

        

        The name of the attribute.

        

        

      Value -> (string)

        

        The value of the attribute.

        

        

      

    

  

