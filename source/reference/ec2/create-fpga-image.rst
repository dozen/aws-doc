[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-fpga-image:


*****************
create-fpga-image
*****************



===========
Description
===========



Creates an Amazon FPGA Image (AFI) from the specified design checkpoint (DCP).

 

The create operation is asynchronous. To verify that the AFI is ready for use, check the output logs.

 

An AFI contains the FPGA bitstream that is ready to download to an FPGA. You can securely deploy an AFI on one or more FPGA-accelerated instances. For more information, see the `AWS FPGA Hardware Development Kit <https://github.com/aws/aws-fpga/>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CreateFpgaImage>`_


========
Synopsis
========

::

    create-fpga-image
  [--dry-run | --no-dry-run]
  --input-storage-location <value>
  [--logs-storage-location <value>]
  [--description <value>]
  [--name <value>]
  [--client-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--input-storage-location`` (structure)


  The location of the encrypted design checkpoint in Amazon S3. The input must be a tarball.

  



Shorthand Syntax::

    Bucket=string,Key=string




JSON Syntax::

  {
    "Bucket": "string",
    "Key": "string"
  }



``--logs-storage-location`` (structure)


  The location in Amazon S3 for the output logs.

  



Shorthand Syntax::

    Bucket=string,Key=string




JSON Syntax::

  {
    "Bucket": "string",
    "Key": "string"
  }



``--description`` (string)


  A description for the AFI.

  

``--name`` (string)


  A name for the AFI.

  

``--client-token`` (string)


  Unique, case-sensitive identifier that you provide to ensure the idempotency of the request. For more information, see `Ensuring Idempotency <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Run_Instance_Idempotency.html>`_ .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

FpgaImageId -> (string)

  

  The FPGA image identifier (AFI ID).

  

  

FpgaImageGlobalId -> (string)

  

  The global FPGA image identifier (AGFI ID).

  

  

