[ :ref:`aws <cli:aws>` . :ref:`route53domains <cli:aws route53domains>` ]

.. _cli:aws route53domains transfer-domain:


***************
transfer-domain
***************



===========
Description
===========



This operation transfers a domain from another registrar to Amazon Route 53. When the transfer is complete, the domain is registered with the AWS registrar partner, Gandi.

 

For transfer requirements, a detailed procedure, and information about viewing the status of a domain transfer, see `Transferring Registration for a Domain to Amazon Route 53`_ in the Amazon Route 53 Developer Guide.

 

If the registrar for your domain is also the DNS service provider for the domain, we highly recommend that you consider transferring your DNS service to Amazon Route 53 or to another DNS service provider before you transfer your registration. Some registrars provide free DNS service when you purchase a domain registration. When you transfer the registration, the previous registrar will not renew your domain registration and could end your DNS service at any time.

 

.. note::

  Caution! If the registrar for your domain is also the DNS service provider for the domain and you don't transfer DNS service to another provider, your website, email, and the web applications associated with the domain might become unavailable.

 

If the transfer is successful, this method returns an operation ID that you can use to track the progress and completion of the action. If the transfer doesn't complete successfully, the domain registrant will be notified by email.



========
Synopsis
========

::

    transfer-domain
  --domain-name <value>
  [--idn-lang-code <value>]
  --duration-in-years <value>
  [--nameservers <value>]
  [--auth-code <value>]
  [--auto-renew | --no-auto-renew]
  --admin-contact <value>
  --registrant-contact <value>
  --tech-contact <value>
  [--privacy-protect-admin-contact | --no-privacy-protect-admin-contact]
  [--privacy-protect-registrant-contact | --no-privacy-protect-registrant-contact]
  [--privacy-protect-tech-contact | --no-privacy-protect-tech-contact]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-name`` (string)


  The name of a domain.

   

  Type: String

   

  Default: None

   

  Constraints: The domain name can contain only the letters a through z, the numbers 0 through 9, and hyphen (-). Internationalized Domain Names are not supported.

   

  Required: Yes

  

``--idn-lang-code`` (string)


  Reserved for future use.

  

``--duration-in-years`` (integer)


  The number of years the domain will be registered. Domains are registered for a minimum of one year. The maximum period depends on the top-level domain.

   

  Type: Integer

   

  Default: 1

   

  Valid values: Integer from 1 to 10

   

  Required: Yes

  

``--nameservers`` (list)


  Contains details for the host and glue IP addresses.

   

  Type: Complex

   

  Children: ``GlueIps`` , ``Name`` 

   

  Required: No

  



Shorthand Syntax::

    Name=string,GlueIps=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "GlueIps": ["string", ...]
    }
    ...
  ]



``--auth-code`` (string)


  The authorization code for the domain. You get this value from the current registrar.

   

  Type: String

   

  Required: Yes

  

``--auto-renew`` | ``--no-auto-renew`` (boolean)


  Indicates whether the domain will be automatically renewed (true) or not (false). Autorenewal only takes effect after the account is charged.

   

  Type: no-privacy-protect-tech-contact

   

  Valid values: ``true`` | ``false`` 

   

  Default: true

   

  Required: No

  

``--admin-contact`` (structure)


  Provides detailed contact information.

   

  Type: Complex

   

  Children: ``FirstName`` , ``MiddleName`` , ``LastName`` , ``ContactType`` , ``OrganizationName`` , ``AddressLine1`` , ``AddressLine2`` , ``City`` , ``State`` , ``CountryCode`` , ``ZipCode`` , ``PhoneNumber`` , ``Email`` , ``Fax`` , ``ExtraParams`` 

   

  Required: Yes

  



Shorthand Syntax::

    FirstName=string,LastName=string,ContactType=string,OrganizationName=string,AddressLine1=string,AddressLine2=string,City=string,State=string,CountryCode=string,ZipCode=string,PhoneNumber=string,Email=string,Fax=string,ExtraParams=[{Name=string,Value=string},{Name=string,Value=string}]




JSON Syntax::

  {
    "FirstName": "string",
    "LastName": "string",
    "ContactType": "PERSON"|"COMPANY"|"ASSOCIATION"|"PUBLIC_BODY"|"RESELLER",
    "OrganizationName": "string",
    "AddressLine1": "string",
    "AddressLine2": "string",
    "City": "string",
    "State": "string",
    "CountryCode": "AD"|"AE"|"AF"|"AG"|"AI"|"AL"|"AM"|"AN"|"AO"|"AQ"|"AR"|"AS"|"AT"|"AU"|"AW"|"AZ"|"BA"|"BB"|"BD"|"BE"|"BF"|"BG"|"BH"|"BI"|"BJ"|"BL"|"BM"|"BN"|"BO"|"BR"|"BS"|"BT"|"BW"|"BY"|"BZ"|"CA"|"CC"|"CD"|"CF"|"CG"|"CH"|"CI"|"CK"|"CL"|"CM"|"CN"|"CO"|"CR"|"CU"|"CV"|"CX"|"CY"|"CZ"|"DE"|"DJ"|"DK"|"DM"|"DO"|"DZ"|"EC"|"EE"|"EG"|"ER"|"ES"|"ET"|"FI"|"FJ"|"FK"|"FM"|"FO"|"FR"|"GA"|"GB"|"GD"|"GE"|"GH"|"GI"|"GL"|"GM"|"GN"|"GQ"|"GR"|"GT"|"GU"|"GW"|"GY"|"HK"|"HN"|"HR"|"HT"|"HU"|"ID"|"IE"|"IL"|"IM"|"IN"|"IQ"|"IR"|"IS"|"IT"|"JM"|"JO"|"JP"|"KE"|"KG"|"KH"|"KI"|"KM"|"KN"|"KP"|"KR"|"KW"|"KY"|"KZ"|"LA"|"LB"|"LC"|"LI"|"LK"|"LR"|"LS"|"LT"|"LU"|"LV"|"LY"|"MA"|"MC"|"MD"|"ME"|"MF"|"MG"|"MH"|"MK"|"ML"|"MM"|"MN"|"MO"|"MP"|"MR"|"MS"|"MT"|"MU"|"MV"|"MW"|"MX"|"MY"|"MZ"|"NA"|"NC"|"NE"|"NG"|"NI"|"NL"|"NO"|"NP"|"NR"|"NU"|"NZ"|"OM"|"PA"|"PE"|"PF"|"PG"|"PH"|"PK"|"PL"|"PM"|"PN"|"PR"|"PT"|"PW"|"PY"|"QA"|"RO"|"RS"|"RU"|"RW"|"SA"|"SB"|"SC"|"SD"|"SE"|"SG"|"SH"|"SI"|"SK"|"SL"|"SM"|"SN"|"SO"|"SR"|"ST"|"SV"|"SY"|"SZ"|"TC"|"TD"|"TG"|"TH"|"TJ"|"TK"|"TL"|"TM"|"TN"|"TO"|"TR"|"TT"|"TV"|"TW"|"TZ"|"UA"|"UG"|"US"|"UY"|"UZ"|"VA"|"VC"|"VE"|"VG"|"VI"|"VN"|"VU"|"WF"|"WS"|"YE"|"YT"|"ZA"|"ZM"|"ZW",
    "ZipCode": "string",
    "PhoneNumber": "string",
    "Email": "string",
    "Fax": "string",
    "ExtraParams": [
      {
        "Name": "DUNS_NUMBER"|"BRAND_NUMBER"|"BIRTH_DEPARTMENT"|"BIRTH_DATE_IN_YYYY_MM_DD"|"BIRTH_COUNTRY"|"BIRTH_CITY"|"DOCUMENT_NUMBER"|"AU_ID_NUMBER"|"AU_ID_TYPE"|"CA_LEGAL_TYPE"|"ES_IDENTIFICATION"|"ES_IDENTIFICATION_TYPE"|"ES_LEGAL_FORM"|"FI_BUSINESS_NUMBER"|"FI_ID_NUMBER"|"IT_PIN"|"RU_PASSPORT_DATA"|"SE_ID_NUMBER"|"SG_ID_NUMBER"|"VAT_NUMBER",
        "Value": "string"
      }
      ...
    ]
  }



``--registrant-contact`` (structure)


  Provides detailed contact information.

   

  Type: Complex

   

  Children: ``FirstName`` , ``MiddleName`` , ``LastName`` , ``ContactType`` , ``OrganizationName`` , ``AddressLine1`` , ``AddressLine2`` , ``City`` , ``State`` , ``CountryCode`` , ``ZipCode`` , ``PhoneNumber`` , ``Email`` , ``Fax`` , ``ExtraParams`` 

   

  Required: Yes

  



Shorthand Syntax::

    FirstName=string,LastName=string,ContactType=string,OrganizationName=string,AddressLine1=string,AddressLine2=string,City=string,State=string,CountryCode=string,ZipCode=string,PhoneNumber=string,Email=string,Fax=string,ExtraParams=[{Name=string,Value=string},{Name=string,Value=string}]




JSON Syntax::

  {
    "FirstName": "string",
    "LastName": "string",
    "ContactType": "PERSON"|"COMPANY"|"ASSOCIATION"|"PUBLIC_BODY"|"RESELLER",
    "OrganizationName": "string",
    "AddressLine1": "string",
    "AddressLine2": "string",
    "City": "string",
    "State": "string",
    "CountryCode": "AD"|"AE"|"AF"|"AG"|"AI"|"AL"|"AM"|"AN"|"AO"|"AQ"|"AR"|"AS"|"AT"|"AU"|"AW"|"AZ"|"BA"|"BB"|"BD"|"BE"|"BF"|"BG"|"BH"|"BI"|"BJ"|"BL"|"BM"|"BN"|"BO"|"BR"|"BS"|"BT"|"BW"|"BY"|"BZ"|"CA"|"CC"|"CD"|"CF"|"CG"|"CH"|"CI"|"CK"|"CL"|"CM"|"CN"|"CO"|"CR"|"CU"|"CV"|"CX"|"CY"|"CZ"|"DE"|"DJ"|"DK"|"DM"|"DO"|"DZ"|"EC"|"EE"|"EG"|"ER"|"ES"|"ET"|"FI"|"FJ"|"FK"|"FM"|"FO"|"FR"|"GA"|"GB"|"GD"|"GE"|"GH"|"GI"|"GL"|"GM"|"GN"|"GQ"|"GR"|"GT"|"GU"|"GW"|"GY"|"HK"|"HN"|"HR"|"HT"|"HU"|"ID"|"IE"|"IL"|"IM"|"IN"|"IQ"|"IR"|"IS"|"IT"|"JM"|"JO"|"JP"|"KE"|"KG"|"KH"|"KI"|"KM"|"KN"|"KP"|"KR"|"KW"|"KY"|"KZ"|"LA"|"LB"|"LC"|"LI"|"LK"|"LR"|"LS"|"LT"|"LU"|"LV"|"LY"|"MA"|"MC"|"MD"|"ME"|"MF"|"MG"|"MH"|"MK"|"ML"|"MM"|"MN"|"MO"|"MP"|"MR"|"MS"|"MT"|"MU"|"MV"|"MW"|"MX"|"MY"|"MZ"|"NA"|"NC"|"NE"|"NG"|"NI"|"NL"|"NO"|"NP"|"NR"|"NU"|"NZ"|"OM"|"PA"|"PE"|"PF"|"PG"|"PH"|"PK"|"PL"|"PM"|"PN"|"PR"|"PT"|"PW"|"PY"|"QA"|"RO"|"RS"|"RU"|"RW"|"SA"|"SB"|"SC"|"SD"|"SE"|"SG"|"SH"|"SI"|"SK"|"SL"|"SM"|"SN"|"SO"|"SR"|"ST"|"SV"|"SY"|"SZ"|"TC"|"TD"|"TG"|"TH"|"TJ"|"TK"|"TL"|"TM"|"TN"|"TO"|"TR"|"TT"|"TV"|"TW"|"TZ"|"UA"|"UG"|"US"|"UY"|"UZ"|"VA"|"VC"|"VE"|"VG"|"VI"|"VN"|"VU"|"WF"|"WS"|"YE"|"YT"|"ZA"|"ZM"|"ZW",
    "ZipCode": "string",
    "PhoneNumber": "string",
    "Email": "string",
    "Fax": "string",
    "ExtraParams": [
      {
        "Name": "DUNS_NUMBER"|"BRAND_NUMBER"|"BIRTH_DEPARTMENT"|"BIRTH_DATE_IN_YYYY_MM_DD"|"BIRTH_COUNTRY"|"BIRTH_CITY"|"DOCUMENT_NUMBER"|"AU_ID_NUMBER"|"AU_ID_TYPE"|"CA_LEGAL_TYPE"|"ES_IDENTIFICATION"|"ES_IDENTIFICATION_TYPE"|"ES_LEGAL_FORM"|"FI_BUSINESS_NUMBER"|"FI_ID_NUMBER"|"IT_PIN"|"RU_PASSPORT_DATA"|"SE_ID_NUMBER"|"SG_ID_NUMBER"|"VAT_NUMBER",
        "Value": "string"
      }
      ...
    ]
  }



``--tech-contact`` (structure)


  Provides detailed contact information.

   

  Type: Complex

   

  Children: ``FirstName`` , ``MiddleName`` , ``LastName`` , ``ContactType`` , ``OrganizationName`` , ``AddressLine1`` , ``AddressLine2`` , ``City`` , ``State`` , ``CountryCode`` , ``ZipCode`` , ``PhoneNumber`` , ``Email`` , ``Fax`` , ``ExtraParams`` 

   

  Required: Yes

  



Shorthand Syntax::

    FirstName=string,LastName=string,ContactType=string,OrganizationName=string,AddressLine1=string,AddressLine2=string,City=string,State=string,CountryCode=string,ZipCode=string,PhoneNumber=string,Email=string,Fax=string,ExtraParams=[{Name=string,Value=string},{Name=string,Value=string}]




JSON Syntax::

  {
    "FirstName": "string",
    "LastName": "string",
    "ContactType": "PERSON"|"COMPANY"|"ASSOCIATION"|"PUBLIC_BODY"|"RESELLER",
    "OrganizationName": "string",
    "AddressLine1": "string",
    "AddressLine2": "string",
    "City": "string",
    "State": "string",
    "CountryCode": "AD"|"AE"|"AF"|"AG"|"AI"|"AL"|"AM"|"AN"|"AO"|"AQ"|"AR"|"AS"|"AT"|"AU"|"AW"|"AZ"|"BA"|"BB"|"BD"|"BE"|"BF"|"BG"|"BH"|"BI"|"BJ"|"BL"|"BM"|"BN"|"BO"|"BR"|"BS"|"BT"|"BW"|"BY"|"BZ"|"CA"|"CC"|"CD"|"CF"|"CG"|"CH"|"CI"|"CK"|"CL"|"CM"|"CN"|"CO"|"CR"|"CU"|"CV"|"CX"|"CY"|"CZ"|"DE"|"DJ"|"DK"|"DM"|"DO"|"DZ"|"EC"|"EE"|"EG"|"ER"|"ES"|"ET"|"FI"|"FJ"|"FK"|"FM"|"FO"|"FR"|"GA"|"GB"|"GD"|"GE"|"GH"|"GI"|"GL"|"GM"|"GN"|"GQ"|"GR"|"GT"|"GU"|"GW"|"GY"|"HK"|"HN"|"HR"|"HT"|"HU"|"ID"|"IE"|"IL"|"IM"|"IN"|"IQ"|"IR"|"IS"|"IT"|"JM"|"JO"|"JP"|"KE"|"KG"|"KH"|"KI"|"KM"|"KN"|"KP"|"KR"|"KW"|"KY"|"KZ"|"LA"|"LB"|"LC"|"LI"|"LK"|"LR"|"LS"|"LT"|"LU"|"LV"|"LY"|"MA"|"MC"|"MD"|"ME"|"MF"|"MG"|"MH"|"MK"|"ML"|"MM"|"MN"|"MO"|"MP"|"MR"|"MS"|"MT"|"MU"|"MV"|"MW"|"MX"|"MY"|"MZ"|"NA"|"NC"|"NE"|"NG"|"NI"|"NL"|"NO"|"NP"|"NR"|"NU"|"NZ"|"OM"|"PA"|"PE"|"PF"|"PG"|"PH"|"PK"|"PL"|"PM"|"PN"|"PR"|"PT"|"PW"|"PY"|"QA"|"RO"|"RS"|"RU"|"RW"|"SA"|"SB"|"SC"|"SD"|"SE"|"SG"|"SH"|"SI"|"SK"|"SL"|"SM"|"SN"|"SO"|"SR"|"ST"|"SV"|"SY"|"SZ"|"TC"|"TD"|"TG"|"TH"|"TJ"|"TK"|"TL"|"TM"|"TN"|"TO"|"TR"|"TT"|"TV"|"TW"|"TZ"|"UA"|"UG"|"US"|"UY"|"UZ"|"VA"|"VC"|"VE"|"VG"|"VI"|"VN"|"VU"|"WF"|"WS"|"YE"|"YT"|"ZA"|"ZM"|"ZW",
    "ZipCode": "string",
    "PhoneNumber": "string",
    "Email": "string",
    "Fax": "string",
    "ExtraParams": [
      {
        "Name": "DUNS_NUMBER"|"BRAND_NUMBER"|"BIRTH_DEPARTMENT"|"BIRTH_DATE_IN_YYYY_MM_DD"|"BIRTH_COUNTRY"|"BIRTH_CITY"|"DOCUMENT_NUMBER"|"AU_ID_NUMBER"|"AU_ID_TYPE"|"CA_LEGAL_TYPE"|"ES_IDENTIFICATION"|"ES_IDENTIFICATION_TYPE"|"ES_LEGAL_FORM"|"FI_BUSINESS_NUMBER"|"FI_ID_NUMBER"|"IT_PIN"|"RU_PASSPORT_DATA"|"SE_ID_NUMBER"|"SG_ID_NUMBER"|"VAT_NUMBER",
        "Value": "string"
      }
      ...
    ]
  }



``--privacy-protect-admin-contact`` | ``--no-privacy-protect-admin-contact`` (boolean)


  Whether you want to conceal contact information from WHOIS queries. If you specify true, WHOIS ("who is") queries will return contact information for our registrar partner, Gandi, instead of the contact information that you enter.

   

  Type: no-privacy-protect-tech-contact

   

  Default: ``true`` 

   

  Valid values: ``true`` | ``false`` 

   

  Required: No

  

``--privacy-protect-registrant-contact`` | ``--no-privacy-protect-registrant-contact`` (boolean)


  Whether you want to conceal contact information from WHOIS queries. If you specify true, WHOIS ("who is") queries will return contact information for our registrar partner, Gandi, instead of the contact information that you enter.

   

  Type: no-privacy-protect-tech-contact

   

  Default: ``true`` 

   

  Valid values: ``true`` | ``false`` 

   

  Required: No

  

``--privacy-protect-tech-contact`` | ``--no-privacy-protect-tech-contact`` (boolean)


  Whether you want to conceal contact information from WHOIS queries. If you specify true, WHOIS ("who is") queries will return contact information for our registrar partner, Gandi, instead of the contact information that you enter.

   

  Type: no-privacy-protect-tech-contact

   

  Default: ``true`` 

   

  Valid values: ``true`` | ``false`` 

   

  Required: No

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

OperationId -> (string)

  

  Identifier for tracking the progress of the request. To use this ID to query the operation status, use GetOperationDetail.

   

  Type: String

   

  Default: None

   

  Constraints: Maximum 255 characters.

  

  



.. _Transferring Registration for a Domain to Amazon Route 53: http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-transfer-to-route-53.html
