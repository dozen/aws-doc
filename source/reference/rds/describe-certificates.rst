[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-certificates:


*********************
describe-certificates
*********************



===========
Description
===========



Lists the set of CA certificates provided by Amazon RDS for this AWS account. 



========
Synopsis
========

::

    describe-certificates
  [--certificate-identifier <value>]
  [--filters <value>]
  [--max-records <value>]
  [--marker <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--certificate-identifier`` (string)


  The user-supplied certificate identifier. If this parameter is specified, information for only the identified certificate is returned. This parameter isn't case-sensitive. 

   

  Constraints:

   

   
  * Must contain from 1 to 63 alphanumeric characters or hyphens
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   

  

``--filters`` (list)


  This parameter is not currently supported.

  



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



``--max-records`` (integer)


  The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

   

  Default: 100

   

  Constraints: Minimum 20, maximum 100.

  

``--marker`` (string)


  An optional pagination token provided by a previous  describe-certificates request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Certificates -> (list)

  

  The list of  Certificate objects for the AWS account.

  

  (structure)

    

    A CA certificate for an AWS account. 

    

    CertificateIdentifier -> (string)

      

      The unique key that identifies a certificate. 

      

      

    CertificateType -> (string)

      

      The type of the certificate. 

      

      

    Thumbprint -> (string)

      

      The thumbprint of the certificate. 

      

      

    ValidFrom -> (timestamp)

      

      The starting date from which the certificate is valid. 

      

      

    ValidTill -> (timestamp)

      

      The final date that the certificate continues to be valid. 

      

      

    

  

Marker -> (string)

  

  An optional pagination token provided by a previous  describe-certificates request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

  

