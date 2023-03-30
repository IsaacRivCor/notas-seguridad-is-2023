# repetitions
## Descripcion
Can you make sense of this file? Download the file [here](https://artifacts.picoctf.net/c/292/enc_flag).

## Pistas
Multiple decoding is always good.

## Solucion 
decodificar el base 64 del archivo dado, hasta encontrar la bandera

original:
VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVh
RmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNk
MlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVW
VkpEVGxaYVdFMVhSbHBWV0VKd1ZtMDFRMDFHV1hsbFJrNVlDbUY2UWpOVVZsSmhZVVpLU0dWRlZs
aGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==
resultado:
VjFSQ2EyTXlSblJUV0dSVllrWmFWRmx0TlZOalJtUlhZVVU1YVZKVVZuaFdWekZoWVZkR2NrNVVX
bUZTVmtwUVdWUkdibVZXVm5WUgpiSEJzWVRCd2VWVXhXbXBOUlRWSFdqTnNWZ3BYUjFKeVZGZHdW
MlZzVWxaVmJFNW9UVVJDTlZaWE1XRlpVWEJwVm01Q01GWXllRk5YCmF6QjNUVlJhYUZKSGVFVlhi
bTkzVDFWT2JsQlVNRXNLCg==

----------------------------------------------------------------
original:
VjFSQ2EyTXlSblJUV0dSVllrWmFWRmx0TlZOalJtUlhZVVU1YVZKVVZuaFdWekZoWVZkR2NrNVVX
bUZTVmtwUVdWUkdibVZXVm5WUgpiSEJzWVRCd2VWVXhXbXBOUlRWSFdqTnNWZ3BYUjFKeVZGZHdW
MlZzVWxaVmJFNW9UVVJDTlZaWE1XRlpVWEJwVm01Q01GWXllRk5YCmF6QjNUVlJhYUZKSGVFVlhi
bTkzVDFWT2JsQlVNRXNLCg==

resultado:
V1RCa2MyRnRTWGRVYkZaVFltNVNjRmRXYUU5aVJUVnhWVzFhYVdGck5UWmFSVkpQWVRGbmVWVnVR
bHBsYTBweVUxWmpNRTVHWjNsVgpXR1JyVFdwV2VsUlZVbE5oTURCNVZXMWFZUXBpVm5CMFYyeFNX
azB3TVRaaFJHeEVXbm93T1VOblBUMEsK

---------------------------------------------------------------------------
original:
V1RCa2MyRnRTWGRVYkZaVFltNVNjRmRXYUU5aVJUVnhWVzFhYVdGck5UWmFSVkpQWVRGbmVWVnVR
bHBsYTBweVUxWmpNRTVHWjNsVgpXR1JyVFdwV2VsUlZVbE5oTURCNVZXMWFZUXBpVm5CMFYyeFNX
azB3TVRaaFJHeEVXbm93T1VOblBUMEsK

resultado:
WTBkc2FtSXdUbFZTYm5ScFdWaE9iRTVxVW1aaWFrNTZaRVJPYTFneVVuQlpla0pyU1ZjME5GZ3lV
WGRrTWpWelRVUlNhMDB5VW1aYQpiVnB0V2xSWk0wMTZhRGxEWnowOUNnPT0K


------------------------------------------------------------------------
original:
WTBkc2FtSXdUbFZTYm5ScFdWaE9iRTVxVW1aaWFrNTZaRVJPYTFneVVuQlpla0pyU1ZjME5GZ3lV
WGRrTWpWelRVUlNhMDB5VW1aYQpiVnB0V2xSWk0wMTZhRGxEWnowOUNnPT0K


resultado:
Y0dsamIwTlVSbnRpWVhObE5qUmZiak56ZEROa1gyUnBZekJrSVc0NFgyUXdkMjVzTURSa00yUmZa
bVptWlRZM016aDlDZz09Cg==

-------------------------------------------------------------------------

original:
Y0dsamIwTlVSbnRpWVhObE5qUmZiak56ZEROa1gyUnBZekJrSVc0NFgyUXdkMjVzTURSa00yUmZa
bVptWlRZM016aDlDZz09Cg==

resultado:
cGljb0NURntiYXNlNjRfbjNzdDNkX2RpYzBkIW44X2Qwd25sMDRkM2RfZmZmZTY3Mzh9Cg==

-------------------------------------------------------------------------
original:
cGljb0NURntiYXNlNjRfbjNzdDNkX2RpYzBkIW44X2Qwd25sMDRkM2RfZmZmZTY3Mzh9Cg==

resultado:
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_fffe6738}

## Bandera
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_fffe6738}


## Notas Adicionales 
https://www.base64decode.org/
