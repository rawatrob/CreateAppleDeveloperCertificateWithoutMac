<h1>Create Apple Developer certificates with Mac</h1>

1.. Generate a certificate signing request <br/>
    <code>openssl req -nodes -newkey rsa:2048 -keyout ios_enterprise.key -out CertificateSigningRequest.certSigningRequest</code>

Use CertificateSigningRequest.certSigningRequest for create  provisioning profiles 
<br/>
<br/>
2. Download the .cer file, saving it to folder
<br/>
3. Convert the .cer file to a .pem file:<br/>
 <code>openssl x509 -in ios_enterprise.cer -inform DER -out ios_enterprise.pem -outform PEM</code>
 <br/>
 
 4. Convert the .pem to a .p12:
 <br/>
 <code>openssl pkcs12 -export -inkey ios_enterprise.key -in ios_enterprise.pem -out ios_enterprise.p12</code>
