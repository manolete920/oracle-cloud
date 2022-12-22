

# Instalar OCI en Ubuntu

https://docs.oracle.com/en-us/iaas/Content/API/SDKDocs/cliinstall.htm#InstallingCLI__linux_and_unix

```bash
bash -c "$(curl -L https://raw.githubusercontent.com/oracle/oci-cli/master/scripts/install/install.sh)"
```

## User/password

```bash
manolete919/M_@n0l3te_919
```

## Verifying the OCI CLI Installation

```bash
oci --version
```

example M@nolete919

```
manolete919@SIS_CEN1_071:~$ oci --version
3.22.0
```

## User profile

```bash
[DEFAULT]
user=ocid1.user.oc1..aaaaaaaac4cyaor6ijegybc5ydcduevzwvyuu3g63i2dmrkz3nbssh2pxsaq
fingerprint=b0:76:fc:9e:47:23:9a:18:46:07:51:7e:aa:28:97:c0
tenancy=ocid1.tenancy.oc1..aaaaaaaazk5fzn3nj4hrz5qgki6tdvhtzmkgggyspun5cyogx24bngwehgma
region=us-ashburn-1
key_file=/home/opc/mgarciarprivate.pem
```

## set up with key file

```bash
[opc@mgr-vm-dev01 ~]$ oci setup config
    This command provides a walkthrough of creating a valid CLI config file.

    The following links explain where to find the information required by this
    script:

    User API Signing Key, OCID and Tenancy OCID:

        https://docs.cloud.oracle.com/Content/API/Concepts/apisigningkey.htm#Other

    Region:

        https://docs.cloud.oracle.com/Content/General/Concepts/regions.htm

    General config documentation:

        https://docs.cloud.oracle.com/Content/API/Concepts/sdkconfig.htm


Enter a location for your config [/home/opc/.oci/config]:
Enter a user OCID: ocid1.user.oc1..aaaaaaaac4cyaor6ijegybc5ydcduevzwvyuu3g63i2dmrkz3nbssh2pxsaq
Enter a tenancy OCID: ocid1.tenancy.oc1..aaaaaaaazk5fzn3nj4hrz5qgki6tdvhtzmkgggyspun5cyogx24bngwehgma
Enter a region by index or name(e.g.
1: af-johannesburg-1, 2: ap-chiyoda-1, 3: ap-chuncheon-1, 4: ap-dcc-canberra-1, 5: ap-hyderabad-1,
6: ap-ibaraki-1, 7: ap-melbourne-1, 8: ap-mumbai-1, 9: ap-osaka-1, 10: ap-seoul-1,
11: ap-singapore-1, 12: ap-sydney-1, 13: ap-tokyo-1, 14: ca-montreal-1, 15: ca-toronto-1,
16: eu-amsterdam-1, 17: eu-frankfurt-1, 18: eu-marseille-1, 19: eu-milan-1, 20: eu-stockholm-1,
21: eu-zurich-1, 22: il-jerusalem-1, 23: me-abudhabi-1, 24: me-dcc-muscat-1, 25: me-dubai-1,
26: me-jeddah-1, 27: sa-santiago-1, 28: sa-saopaulo-1, 29: sa-vinhedo-1, 30: uk-cardiff-1,
31: uk-gov-cardiff-1, 32: uk-gov-london-1, 33: uk-london-1, 34: us-ashburn-1, 35: us-gov-ashburn-1,
36: us-gov-chicago-1, 37: us-gov-phoenix-1, 38: us-langley-1, 39: us-luke-1, 40: us-phoenix-1,
41: us-sanjose-1): us-ashburn-1
Do you want to generate a new API Signing RSA key pair? (If you decline you will be asked to supply the path to an existing key.) [Y/n]: n
Enter the location of your API Signing private key file: /home/opc/mgarciarprivate.pem
Fingerprint: b0:76:fc:9e:47:23:9a:18:46:07:51:7e:aa:28:97:c0
Config written to /home/opc/.oci/config


    If you haven't already uploaded your API Signing public key through the
    console, follow the instructions on the page linked below in the section
    'How to upload the public key':

        https://docs.cloud.oracle.com/Content/API/Concepts/apisigningkey.htm#How2


```

output

```bash
[opc@mgr-vm-dev01 ~]$ cd .oci/
[opc@mgr-vm-dev01 .oci]$ ls
config
[opc@mgr-vm-dev01 .oci]$ cat config
[DEFAULT]
user=ocid1.user.oc1..aaaaaaaac4cyaor6ijegybc5ydcduevzwvyuu3g63i2dmrkz3nbssh2pxsaq
fingerprint=b0:76:fc:9e:47:23:9a:18:46:07:51:7e:aa:28:97:c0
key_file=/home/opc/mgarciarprivate.pem
tenancy=ocid1.tenancy.oc1..aaaaaaaazk5fzn3nj4hrz5qgki6tdvhtzmkgggyspun5cyogx24bngwehgma
region=us-ashburn-1
```



## oci os ns get

```bash
[opc@mgr-vm-dev01 .oci]$ oci os ns get
WARNING: Permissions on /home/opc/mgarciarprivate.pem are too open.
To fix this please try executing the following command:
oci setup repair-file-permissions --file /home/opc/mgarciarprivate.pem
Alternatively to hide this warning, you may set the environment variable, OCI_CLI_SUPPRESS_FILE_PERMISSIONS_WARNING:
export OCI_CLI_SUPPRESS_FILE_PERMISSIONS_WARNING=True

{
  "data": "id6dibaakt36"
}
```



## Set up generating key file

```bash
manolete919@SIS_CEN1_071:~$ oci setup config
    This command provides a walkthrough of creating a valid CLI config file.

    The following links explain where to find the information required by this
    script:

    User API Signing Key, OCID and Tenancy OCID:

        https://docs.cloud.oracle.com/Content/API/Concepts/apisigningkey.htm#Other

    Region:

        https://docs.cloud.oracle.com/Content/General/Concepts/regions.htm

    General config documentation:

        https://docs.cloud.oracle.com/Content/API/Concepts/sdkconfig.htm


Enter a location for your config [/home/manolete919/.oci/config]:
Enter a user OCID: ocid1.user.oc1..aaaaaaaac4cyaor6ijegybc5ydcduevzwvyuu3g63i2dmrkz3nbssh2pxsaq
Enter a tenancy OCID: ocid1.tenancy.oc1..aaaaaaaazk5fzn3nj4hrz5qgki6tdvhtzmkgggyspun5cyogx24bngwehgma
Enter a region by index or name(e.g.
1: af-johannesburg-1, 2: ap-chiyoda-1, 3: ap-chuncheon-1, 4: ap-dcc-canberra-1, 5: ap-hyderabad-1,
6: ap-ibaraki-1, 7: ap-melbourne-1, 8: ap-mumbai-1, 9: ap-osaka-1, 10: ap-seoul-1,
11: ap-singapore-1, 12: ap-sydney-1, 13: ap-tokyo-1, 14: ca-montreal-1, 15: ca-toronto-1,
16: eu-amsterdam-1, 17: eu-dcc-milan-1, 18: eu-frankfurt-1, 19: eu-madrid-1, 20: eu-marseille-1,
21: eu-milan-1, 22: eu-paris-1, 23: eu-stockholm-1, 24: eu-zurich-1, 25: il-jerusalem-1,
26: me-abudhabi-1, 27: me-dcc-muscat-1, 28: me-dubai-1, 29: me-jeddah-1, 30: mx-queretaro-1,
31: sa-santiago-1, 32: sa-saopaulo-1, 33: sa-vinhedo-1, 34: uk-cardiff-1, 35: uk-gov-cardiff-1,
36: uk-gov-london-1, 37: uk-london-1, 38: us-ashburn-1, 39: us-gov-ashburn-1, 40: us-gov-chicago-1,
41: us-gov-phoenix-1, 42: us-langley-1, 43: us-luke-1, 44: us-phoenix-1, 45: us-sanjose-1): 38
Do you want to generate a new API Signing RSA key pair? (If you decline you will be asked to supply the path to an existing key.) [Y/n]: Y
Enter a directory for your keys to be created [/home/manolete919/.oci]:
Enter a name for your key [oci_api_key]:
Public key written to: /home/manolete919/.oci/oci_api_key_public.pem
Enter a passphrase for your private key (empty for no passphrase):
Private key written to: /home/manolete919/.oci/oci_api_key.pem
Fingerprint: 24:75:77:7b:c7:77:15:5a:1b:53:48:3d:e1:a0:cb:f9
Config written to /home/manolete919/.oci/config


    If you haven't already uploaded your API Signing public key through the
    console, follow the instructions on the page linked below in the section
    'How to upload the public key':

        https://docs.cloud.oracle.com/Content/API/Concepts/apisigningkey.htm#How2


manolete919@SIS_CEN1_071:~$ ls
bin  lib  openshift4
manolete919@SIS_CEN1_071:~$ cat /home/manolete919/.oci/oci_api_key.pem
-----BEGIN PRIVATE KEY-----
MIIEvgIBADANBgkqhkiG9w0BAQEFAASCBKgwggSkAgEAAoIBAQDCOarbkKG4M5l7
F9Qx5WW5wVmVnUkwE+zofIN3sCISsVdDf/hy5DjaMdgRG9atgxhtyykdg01ATC2N
S+pFpa8yqFfXbLcq820Zr2OmjY/l9B5iMVbK54CJk03vaqfKK1nbseipmDrK6lyk
HeBPQpQnscuTEyodg8OiAxlikThHYiyt7Lzoi4becnEzu2DgJF7UZtISSf02mpsB
v/eyycM4kLRNoeQmvkWXLwMtTIJPBmMCoj4qp75By7dE/T//WE6Pd15nvStMb3/G
32Tv8pXylcpBIfbh1NGEm88LrQb1L1KkjDzRYelSQIbWm7m8OYPYLBP3kRpGT4Gz
lDwv09VbAgMBAAECggEAHRGFbUwVsBxk5aPY2cjj8yupbTd3my74P4lXIcQmLVcG
YO9Xr1ZR3fIkzNa2SAy9TL1hv22F09Ay5xlMDDVyZaoFT5QRS+fX1cbGqsg4F6n0
HC0XONHyDmUR/nmfeCYJ0lQrpqpGblUqHVPtXN9xjglRlwcAwB8W2foNxA9I9YHM
gOeGMmIfqjZbMbs2pTfghugcnJxB2Xettde6xnFMhFt6WaLaA/H2KSu8xDJhzd5J
atCtQ/NFfUjPYM+qf6Z0fifB1pbj/8I7ghfd06macnLBaS0ks+CcssFo230PM0CX
qwNmLQOAu/OPBPB9/V0yCeDRyegqwMEc6MbEI7sgbQKBgQDzAC5+yVE1LuMl2JMm
QBrmIXWuf5D3vBPqb7dUx7VFSoTXfPG8iuZmvLBuGVU9MHRXUv7dekc6R0RHWjc6
W0E3yndjxYWOZi+HadzK7PdzhGhOq9gY/Y0k3JZ7F8ixoOcfdQu5RNi9ALcYiiZI
vjztxUeT/YaOMP2bAD1aV/4ITwKBgQDMnYV5EiFhJCJN0fqcGL9/ivQTH9xjP9cI
ig/S5fZptiQDNH0PdWzHvRh+m5b2L+KlwCgr4r+p+n7BNv8y2cQCb1V0wjkBxXMN
t68mSMlpV5vtgreUmlgTgY9XPnK99IpQFp00psmewRsbk0sYpeUcqyme84fLyCwh
ZuNx5q3TNQKBgQCobMfNONwAcK8f3Cyhpmz+dNKMT/66trFXHHeFW6ZYkH3inccv
V1a6fq4KoaRi9OKuY+giuk4EJsE8c1s0J2vcr4hwrscTG+B1ivpt7DDW8D8byB/P
sm3RztK+Ho4MD+oh845cq0tONOCzMY23faPdaY9jE6XfiDU+6bucksCQIQKBgQCu
WKI8MUij3wgjywGBNE0nvhyOlx1QrDrrmcg16aB3Hq281WKiY2nXH7bZWnXdO5wh
o4QXMNQjX7/VnqkAiTFM6dSk8kFk0vtf+t2Q/4Au9Gl2jWUjiAf4RvL+YcWfOdkI
uNwm2t79GImii3T3gZOhQ+7o85UH/H4tz9+JVAdU6QKBgA2FQ5KWtJIWVGWXcQZy
/86KLK0+UaZc42YVxRhw+OZHb8kBC8IeGZ9XE5ke6qAyvRem9AAbLEMiHgpKggKh
Z/4cAya4r1XduHuFlMA7DkwB6HimxIqFhPJGhGxA84XkBdx2VaaFGsNjj4Noyf45
Mhdpc1BHpEQBoLNTbPPMWlAh
-----END PRIVATE KEY-----
manolete919@SIS_CEN1_071:~$ cd /home/manolete919/.oci/
manolete919@SIS_CEN1_071:~/.oci$ ls
config  oci_api_key.pem  oci_api_key_public.pem
manolete919@SIS_CEN1_071:~/.oci$ cat oci_api_key_public.pem
-----BEGIN PUBLIC KEY-----
MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAwjmq25ChuDOZexfUMeVl
ucFZlZ1JMBPs6HyDd7AiErFXQ3/4cuQ42jHYERvWrYMYbcspHYNNQEwtjUvqRaWv
MqhX12y3KvNtGa9jpo2P5fQeYjFWyueAiZNN72qnyitZ27HoqZg6yupcpB3gT0KU
J7HLkxMqHYPDogMZYpE4R2Isrey86IuG3nJxM7tg4CRe1GbSEkn9NpqbAb/3ssnD
OJC0TaHkJr5Fly8DLUyCTwZjAqI+Kqe+Qcu3RP0//1hOj3deZ70rTG9/xt9k7/KV
8pXKQSH24dTRhJvPC60G9S9SpIw80WHpUkCG1pu5vDmD2CwT95EaRk+Bs5Q8L9PV
WwIDAQAB
-----END PUBLIC KEY-----
manolete919@SIS_CEN1_071:~/.oci$

```

## authenticate vi console

```bash
manolete919@SIS_CEN1_071:~/.oci$ oci session authenticate
Enter a region by index or name(e.g.
1: af-johannesburg-1, 2: ap-chiyoda-1, 3: ap-chuncheon-1, 4: ap-dcc-canberra-1, 5: ap-hyderabad-1,
6: ap-ibaraki-1, 7: ap-melbourne-1, 8: ap-mumbai-1, 9: ap-osaka-1, 10: ap-seoul-1,
11: ap-singapore-1, 12: ap-sydney-1, 13: ap-tokyo-1, 14: ca-montreal-1, 15: ca-toronto-1,
16: eu-amsterdam-1, 17: eu-dcc-milan-1, 18: eu-frankfurt-1, 19: eu-madrid-1, 20: eu-marseille-1,
21: eu-milan-1, 22: eu-paris-1, 23: eu-stockholm-1, 24: eu-zurich-1, 25: il-jerusalem-1,
26: me-abudhabi-1, 27: me-dcc-muscat-1, 28: me-dubai-1, 29: me-jeddah-1, 30: mx-queretaro-1,
31: sa-santiago-1, 32: sa-saopaulo-1, 33: sa-vinhedo-1, 34: uk-cardiff-1, 35: uk-gov-cardiff-1,
36: uk-gov-london-1, 37: uk-london-1, 38: us-ashburn-1, 39: us-gov-ashburn-1, 40: us-gov-chicago-1,
41: us-gov-phoenix-1, 42: us-langley-1, 43: us-luke-1, 44: us-phoenix-1, 45: us-sanjose-1): 38
    Please switch to newly opened browser window to log in!
    You can also open the following URL in a web browser window to continue:
https://login.us-ashburn-1.oraclecloud.com/v1/oauth2/authorize?action=login&client_id=iaas_console&response_type=token+id_token&nonce=e66b03ca-2131-4121-98b4-7ef01e2090fb&scope=openid&public_key=eyJrdHkiOiAiUlNBIiwgIm4iOiAibUFmbzJSZU1WSzlvSGRCamlKT2xmQTcza0p1MHNjNzJsYkJBdTl6VHJxejVZdC1Ya3JyV1U2dy1nV1VZWlFNdkcxcWlXLUxPeWNRYzRId3NVXzZVM3FPRmNNR0lhQmdvOEU1WS1mWWh2RW1feGgxMVNwODdWLW9Za2x0T0diN0VXa05iS1RYb3dNMExFRzRfQjc3TGpKRGx5T29lVnk3eEhUR0dKbWhlb19qS24ybXhCYXBPS3ZUaHJfRUh5aTFvV2lQSERkUGtwU0pLRUdPclRFQmlOcEJFYnEzR2NxN1I2Ym5hX0ZiM1o3anNHMmp1bVZ2eVBKU3Y2RmRWZUxjUGpIdlp0UFZqcmE3am9BbjJJWENSR0pYcktfZ1F5TlFrM1dmdzdILWgzeHJjT2RORlFmZGotbzROZElELWEya002VlRoNEhNX2R6Z2ZIX01fbDU5S19RIiwgImUiOiAiQVFBQiIsICJraWQiOiAiSWdub3JlZCJ9&redirect_uri=http%3A%2F%2Flocalhost%3A8181
    Completed browser authentication process!
Enter the name of the profile you would like to create: test
Config written to: /home/manolete919/.oci/config

    Try out your newly created session credentials with the following example command:

    oci iam region list --config-file /home/manolete919/.oci/config --profile test --auth security_token
```

