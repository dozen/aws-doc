[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-key-pairs:


******************
describe-key-pairs
******************



===========
Description
===========



Describes one or more of your key pairs.

 

For more information about key pairs, see `Key Pairs <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeKeyPairs>`_


========
Synopsis
========

::

    describe-key-pairs
  [--filters <value>]
  [--key-names <value>]
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  One or more filters.

   

   
  * ``fingerprint`` - The fingerprint of the key pair. 
   
  * ``key-name`` - The name of the key pair. 
   

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--key-names`` (list)


  One or more key pair names.

   

  Default: Describes all your key pairs.

  



Syntax::

  "string" "string" ...



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To display a key pair**

This example displays the fingerprint for the key pair named ``MyKeyPair``.

Command::

  aws ec2 describe-key-pairs --key-name MyKeyPair

Output::

  {
      "KeyPairs": [
          {
              "KeyName": "MyKeyPair",
              "KeyFingerprint": "1f:51:ae:28:bf:89:e9:d8:1f:25:5d:37:2d:7d:b8:ca:9f:f5:f1:6f"
          }
      ]
  }

For more information, see `Using Key Pairs`_ in the *AWS Command Line Interface User Guide*.

.. _`Using Key Pairs`: http://docs.aws.amazon.com/cli/latest/userguide/cli-ec2-keypairs.html



======
Output
======

KeyPairs -> (list)

  

  Information about one or more key pairs.

  

  (structure)

    

    Describes a key pair.

    

    KeyFingerprint -> (string)

      

      If you used  create-key-pair to create the key pair, this is the SHA-1 digest of the DER encoded private key. If you used  import-key-pair to provide AWS the public key, this is the MD5 public key fingerprint as specified in section 4 of RFC4716.

      

      

    KeyName -> (string)

      

      The name of the key pair.

      

      

    

  

