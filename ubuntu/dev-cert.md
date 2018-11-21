# How to trust the .NET Core SDK dev certificate
Install the cert utilities.
```
sudo apt install libnss3-tools
```
Export the already installed certificate.
```
dotnet dev-certs https -v -ep devcert.pfx -p <password>
```
Extract the certificate.
```
openssl pkcs12 -in devcert.pfx -nokeys -out devcert.crt
```
Trust the dev certificate.
```
certutil -d sql:$HOME/.pki/nssdb -A -t "P,," -n "localhost" -i devcert.crt
```
