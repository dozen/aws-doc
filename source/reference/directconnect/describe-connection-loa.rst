[ :ref:`aws <cli:aws>` . :ref:`directconnect <cli:aws directconnect>` ]

.. _cli:aws directconnect describe-connection-loa:


***********************
describe-connection-loa
***********************



===========
Description
===========



Deprecated in favor of  describe-loa .

 

Returns the LOA-CFA for a Connection.

 

The Letter of Authorization - Connecting Facility Assignment (LOA-CFA) is a document that your APN partner or service provider uses when establishing your cross connect to AWS at the colocation facility. For more information, see `Requesting Cross Connects at AWS Direct Connect Locations <http://docs.aws.amazon.com/directconnect/latest/UserGuide/Colocation.html>`_ in the AWS Direct Connect user guide.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/directconnect-2012-10-25/DescribeConnectionLoa>`_


========
Synopsis
========

::

    describe-connection-loa
  --connection-id <value>
  [--provider-name <value>]
  [--loa-content-type <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--connection-id`` (string)


  The ID of the connection. This field is also used as the ID type for operations that use multiple connection types (LAG, interconnect, and/or connection).

   

  Example: dxcon-fg5678gh

   

  Default: None

  

``--provider-name`` (string)


  The name of the APN partner or service provider who establishes connectivity on your behalf. If you supply this parameter, the LOA-CFA lists the provider name alongside your company name as the requester of the cross connect.

   

  Default: None

  

``--loa-content-type`` (string)


  A standard media type indicating the content type of the LOA-CFA document. Currently, the only supported value is "application/pdf".

   

  Default: application/pdf

  

  Possible values:

  
  *   ``application/pdf``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe your LOA-CFA for a connection using Linux or Mac OS X**

The following example describes your LOA-CFA for connection ``dxcon-fh6ayh1d``. The contents of the LOA-CFA are base64-encoded. This command uses the ``--output`` and ``--query`` parameters to control the output and extract the contents of the ``loaContent`` structure. The final part of the command decodes the content using the ``base64`` utility, and sends the output to a PDF file.

.. code::

  aws directconnect describe-connection-loa --connection-id dxcon-fh6ayh1d --output text --query loa.loaContent|base64 --decode > myLoaCfa.pdf

**To describe your LOA-CFA for a connection using Windows**

The previous example requires the use of the ``base64`` utility to decode the output. On a Windows computer, you can use ``certutil`` instead. In the following example, the first command describes your LOA-CFA for connection ``dxcon-fh6ayh1d`` and uses the ``--output`` and ``--query`` parameters to control the output and extract the contents of the ``loaContent`` structure to a file called ``myLoaCfa.base64``. The second command uses the ``certutil`` utility to decode the file and send the output to a PDF file.

.. code::

  aws directconnect describe-connection-loa --connection-id dxcon-fh6ayh1d --output text --query loa.loaContent > myLoaCfa.base64 

.. code::

  certutil -decode myLoaCfa.base64 myLoaCfa.pdf
  
For more information about controlling AWS CLI output, see `Controlling Command Output from the AWS Command Line Interface <https://docs.aws.amazon.com/cli/latest/userguide/controlling-output.html>`_ in the *AWS Command Line Interface User Guide*.

======
Output
======

loa -> (structure)

  

  A structure containing the Letter of Authorization - Connecting Facility Assignment (LOA-CFA) for a connection.

  

  loaContent -> (blob)

    

    The binary contents of the LOA-CFA document.

    

    

  loaContentType -> (string)

    

    A standard media type indicating the content type of the LOA-CFA document. Currently, the only supported value is "application/pdf".

     

    Default: application/pdf

    

    

  

