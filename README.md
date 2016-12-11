# P5-Linux-Server-Configuration
Configure a linux server to host a web application using apache2, mod_wsgi, flask and postgres

### System Info
* Server: AWS
* IP: 35.165.47.126
* SSH Port: 2200
* Login: grader
* Password: fsndUd@1

### Software Summary
1. Apache2
2. Flask
3. mod_wsgi
4. Postgres
5. Finger

### Users Created:
1. grader
2. student

### AWS Item Catalog Public Endpoint
http://ec2-35-165-47-126.us-west-2.compute.amazonaws.com/

### List Of Configurations Made
1. updated the system and its packages
1. added couple of new users student and grader
1. Disabled remote root login
1. Enabled key based authentication
1. Disabled password authentication
1. Gave sudo permissions to the new users
1. Enabled remote login via pub key for the new users
1. Changed default SSH port to 2200
1. Updated firewall rules using ufw (www, ntp, 2200)
1. Added a new wsgi site item-catalog in apache2 sites-available
1. Installed postgres, created users, role, database etc.,
1. Installed flask and supporting packages for item-catalog to run

### Steps taken to deploy
1. cd into /etc/apache2/sites-available
1. Make a new site conf file called ItemCatalog.conf
1. Edit the file and add a new virtual host listening on port 80
1. Include configuration details in the files such as WSGIScriptAlias etc.,
1. cd into /var/www and clone item-catalog project from git
1. Set the $PYTHONPATH to include the project folder so that apache can find it
1. Under the item-catalog project folder, create a app.wsgi script file which will import the application
1. Create user, database, grant permissions in Postgres
1. set database url as environment variable in /etc/apache2/envvars
1. Test the application by accessing the public IP

### User `garder`s RSA key (no passphrase):
```shell
-----BEGIN RSA PRIVATE KEY-----
MIIEowIBAAKCAQEAlnuVkD5DXybY8OrvOes7AsbkM1JHXEkxg12HWvx1Oi8Btlu3
O46+mCzdp3BizLW6c4JVNvI+6Jp/o+HGu5mWNTAOy78mgQCYN0cqtksHvkN7/F7+
k9u6GLVWCx1ayfkBhz/7hO0yMYnqJLG65XE9YO7pZqYINNfyD/4fE0VIEzk3w2fl
+fAT4Ctj9Q0YwB1VWBLXhf62qkydlZrVM8G8GV5MfPwxO2VolSfjRa02Gu0LKu2C
YfZtbSIXBly5/N7pMTr88D86Be9EneSPyUe+9cU7slbbTirMTkq4YOlPCcga5tQq
lr46FS3tnvqZayVZxfcvQ23fWmxMjLu+Z5hErwIDAQABAoIBADPXFTogyPLRnjC4
rnsEd0rIm7q2YJEBQgZgRQ3qJLRLl0psJB5nWW9xHVbeV5rwC/BY+OQ55cQZ3Vjm
oaDlEyL1kFNOYYRVYRrB8IvmIx+/fcn+K7NiIaT7a03e6fTkTEt8ljg/wmfgfAHy
HFGIhj2LcGqFThRuRByQTcJEvsSoDTc4Ljqs3WPtX5T/nwgQ1kEAG9lowawy9YZT
PN5BMKWva1VXk0bEyYfE8iplgpzieZg+3cjrM/o6MHSviGYKvbYv+adTgCmxNNgz
6FeSi/mqGdBaOxJeKG8SVQV57qKlzjDxgz76s8pOSiaqSLiF5WTbJWuRjFZ3ODYA
O+lOp8kCgYEAx1ft6Kfq22f+EJ3dbs15pc3A4pesMDt/6Y+YR80bW2EmDvkwecZO
zKpuvs1dLr/ekshJYlG/bFjpJAiWhs1sA5GUQEPKsosYvUvvEkTeg104/gWDb2Dr
vVZI7GoGTY/ZfVvj1rPXdDaFoLU1W1HPyYon2vmCr/ijWAfs7SVqdsMCgYEAwUCW
iTYAL3IriiBTcB9ibSE59xc/ys6swMydYkMOZC3txuxXllIsxfppNBRxTvrA7c21
ti60m3Fhrq/OvLtewwGuJ40oap611/VShTjn9lisrSHPPnktkI8uTRhE6qIOQ6la
b4ZxrY8UYNvi+vaM9Ip/COv8q7yAdRmpLzId06UCgYAo/i8Bag6E4gTAHAaeM4jx
jLc+oZwaKxIp0IqrMUWP7BFsgNf0ItCvi9jMSeUAqRo3KxLUMiVgPYRsEYwK2pF8
xmIrOQWk46/JtaTLJ/huISyIKFAYBmFUBTtnyoHTT2KVQeE/lKoYzuF54+m+Brvp
IQ0DHc4/K61DfBW/yrLzCwKBgEkgRpZPL8zEWANhbhFMXvNKkmOUkZgNksM16gwH
scdotcQDJLWGDNkxg2OopKOtMRoLMEpq6/6x7bOrZQB3qkkCNsNSn8uQmODKPNqa
iPPn5BdzZreOJRbBh1S27UUX42vpBoaTCisRrDVmn0I1z2qtiZp3qdnWb4lgF2v7
e9vdAoGBAKdzR/wRHeCLSICb21DbRerdeGnx5gZim/doYNGZ02wn3crf5+c4m8Zd
VvBmhpbg4WA6Ljscuh52kavlmtNt9r8NPkJjtO/qaAK4+BQ71765iiTXm1B3alD9
Rw4+wVQt23IJCnUOrc8otxaBDTV28VuXZ0YOfkx8X1HHMYNC2Zay
-----END RSA PRIVATE KEY-----
```

### Udacity RSA Key:
```shell
-----BEGIN RSA PRIVATE KEY-----
MIIEpQIBAAKCAQEA5Kw2SbLjAkcmiphez4GmfoUidXS4j7C23knb2rEOtzCcpC2z
YC+3K0Nm1bHyu0tzDlSJz0KVSklAvuDqYay18XCcuLO7fPoPxIp+cb0kAQ4x50Ph
1IyEIYrROGmiz9JbOS/n93K7JRDvvw6oPWfNGKnurno7ZheWgKtQreBVUCOAQSIw
QF7DztNkq/ZEheJ17yL397Xq46GeVWSNQ1Pe5oIMQ8GdrfcjrMFuFxdFBTEJ0i9A
vcUHEAlpkUYIf6V34hIfvr0sUSCbX4Ohn1HQVAE82pO8TZb0B3IhRy4O8Sj4n0m6
CQOc+Dg1/tMvMgHAkuq0ITqI/1U77e9YBYerTwIDAQABAoIBAQDSIm7AyuJQ9ZE1
S0/U4A9ftHg190yivoFNRBIEpTAgp0tKk7SCb1ajKw0U0rF765mPUaBSFZ2a5jXZ
MlYv68ZGWHWsRX3FGwXiVmJborOzRJgXLQoZiAbjy+z3KhuzXlr18k/31DalmSq3
J4Dy7LBMOdxb+XccGhDzrHo3Ti8Xs8swv1V8ZwekGP1odGIUsr4GxDfyIb0xKgQL
EKOmTyiPg6PymMi2NieYxuDK9ySjn3EgU6UClP3zNzZdQSTIUTpc1CvkFxzhnr15
HUG6enJYDSqF6CC2zymbWoqRY+SefQO3WpA3DhgZZ+EdTsCqVsBT8vqSjS9V/T+5
JrQ+FDYBAoGBAPUWPD1Op1xte0fV1eV1b7DDSXvtccE5dqMJ/q8JXGIls6fd2wU8
Yabwju+5k5sSZgdXkm1V2tlY9l91fdakVNfgsBj1ZaUsy7l1kTGPPMqlBW+NGkaw
8Db6u3DMbTsXrqhJ6qRmg7/44QnEZfQUxszOnrRG6sY1s0GTfuAQlqtrAoGBAO7a
3tljuHmPdEN2JyC52PtWR6uwpvz3zs1dQ+9ndJFMc9o81b+OJ3OxqWhA2OKxe8Ew
DONcyUIVhasTYnBjYgZfc2aU0sNLzC5CP/6EQ5/bmh/s0SrwPVEjARH1hdW+ZtpQ
EuDIL4s21sm5RWJRovdk3GWTi5qliFAXFFKHinytAoGAKRZ4NOL5xdII5+sed+Bv
QBgNOrx85KLok766Nsf/9+hQLSVRcZhE2sLbg6794vJ7rmFtB+1ryiJS83/z/8b+
/k4J17VUPBO9d7MRC1jzHRn7Rk9Gh3FkZCM2x1tOOKjovAfgUX1qOwXTXFrTqM7O
4UkGbDyzYVVhXu4GSDQfvk8CgYEAj51gMtuntsePg2SOYDn+ghi9nTjpHt8tJAO4
7kCJMTgDzKuZZcTmacTf9ERRY/SNUXo/tZE7nZVtOpC8NpE7BlPsAjjnhO+VRBcn
fTQvqPWUdS+iEKxEYf2nDhJPN1Z1ZzyQLUGQfKcrfDz+wAAP+apWbmjJnuF61ZUa
7gh7Nz0CgYEAmNg6DWgVNMnF4CsVzbt4IYes6B4NK2DUkEsTD/3Vkob7no8bTRN3
id3xJy+rdE2qoyqU8NH93OF8VmNFLQJB6U3ovvHws60bGQIjys0jPczd0dR2WFE5
uXFVnfNNxZN+YwnlnofHs1920OPuwz6ThuHaxFYn43gqtH9zrkifSHw=
-----END RSA PRIVATE KEY-----
```


### Third Party Resources:
* https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps
* http://flask.pocoo.org/docs/0.11/deploying/mod_wsgi/
* https://httpd.apache.org/docs/2.4/vhosts/name-based.html
