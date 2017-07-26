[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds create-computer:


***************
create-computer
***************



===========
Description
===========



Creates a computer account in the specified directory, and joins the computer to the directory.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ds-2015-04-16/CreateComputer>`_


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
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

        

        

      

    

  

