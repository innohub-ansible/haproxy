# InnoHub Ansible :  haproxy
=========

* Creates an haproxy deployment
* When SSL option is enabled, sets up SSL certificates and key
* Sets up an haproxy user

Role Variables
--------------

haproxy_version : Not Required : Defaults to 1.5

haproxy_app_name : Required : Identifies application name

haproxy_ssl : Not Required : Activates haproxy's SSL option : Defaults to false

haproxy_ssl_pem : Not Required : Sets haproxy's SSL certificate and private key

    -----BEGIN CERTIFICATE-----
    MIIB+zCCAWQCCQCCWEJqWVLYXDANBgkqhkiG9w0BAQUFADBCMQswCQYDVQQGEwJY
    WDEVMBMGA1UEBwwMRGVmYXVsdCBDaXR5MRwwGgYDVQQKDBNEZWZhdWx0IENvbXBh
    bnkgTHRkMB4XDTE1MDUxODA5MzMyMVoXDTE2MDUxNzA5MzMyMVowQjELMAkGA1UE
    BhMCWFgxFTATBgNVBAcMDERlZmF1bHQgQ2l0eTEcMBoGA1UECgwTRGVmYXVsdCBD
    b21wYW55IEx0ZDCBnzANBgkqhkiG9w0BAQEFAAOBjQAwgYkCgYEA3zavC57RxfVP
    bmIKBPslpsRMf+dF9oWLV/8DekvEnKl2W6MTjShsnQKF4JyoLduB/8obmSy8OQMN
    wD5CnTaV2oCtMV++T9WtCtbrvlK1NVQXvACREBtI09f+6myYAEr42eglCQIVxua7
    77UAiaO923uEyewpTlr4u35GeNCUUxUCAwEAATANBgkqhkiG9w0BAQUFAAOBgQBD
    FnlQTQnR/5uV3O4L6wtdiTTAbj0kDtY+kFLCjSMyDf6WbNczv9ZILJKcfB78xgxE
    5ppszdr6i34EPkng3dlJINwtwm+cE8wW4vMIakBeuXaewfHywPgLBnrsldsFAJeI
    4iaHuCnl49v3Geg4r9T2Jhv/QU1lxJsS/txEj244uA==
    -----END CERTIFICATE-----
    -----BEGIN RSA PRIVATE KEY-----
    MIICXgIBAAKBgQDfNq8LntHF9U9uYgoE+yWmxEx/50X2hYtX/wN6S8ScqXZboxON
    KGydAoXgnKgt24H/yhuZLLw5Aw3APkKdNpXagK0xX75P1a0K1uu+UrU1VBe8AJEQ
    G0jT1/7qbJgASvjZ6CUJAhXG5rvvtQCJo73be4TJ7ClOWvi7fkZ40JRTFQIDAQAB
    AoGBAJ511qycMfWjoaEOLmi81kzenCRMzeklgveUTSa7tTc2QpTpX07dfMW17c63
    x9jONSqekxsZnAGpPlDUojuzbYteWDB6Rxef/3c2+uGlJWw0DQQbimXzRuyqwwuy
    ynaHnCy6HhY+jBIp77RC96BQ5vHqN73Dt2bfEDLqqQwh5BWhAkEA791qJMJnBXjH
    PjzhrkF+/k6MbEZuxE+asfUPa9dDGHHeqIPe6ySwxaCfP8vYcPpJUi7dtrpRwsP7
    VogDb+4FfQJBAO46hrCiMtNpXHhr/jk3CmjRSkB+DwKd3IRhCIOryLl7MBpphwhw
    7mQMwmG3hYigtAAdCIWK1jI1FLNfoB7jl3kCQQDgH47yUgNZBYWGDfUBkYlLrbFf
    6l/NZmQxK74BEd5LlPprkuxT4rCZuH+UaLAQwIyKEehwuJ900RKjw+sSRuExAkEA
    t8PZxkM4JbCurg3QC16T3wsi1eDnv0L6qfsX0EohCkMmdhlVGoPSwMa+4xXoId6l
    OzkqK6lPVWdw0nU/VNSHMQJAKCdsUCy4Y8+neOXW9AcL95tlzwQ3C2dlbSadea2Y
    gAGrLMnFDWkogejrk5xVswlMUzjV6TefJAeQDHA1HIIR5g==
    -----END RSA PRIVATE KEY-----

haproxy_stats : Not Required : Defaults to enable

haproxy_algorithm : Not Required : Defaults to roundrobin

haproxy_chk_host : Not Required : Defines host for http check : Defaults to haproxy_app_name

haproxy_chk_path : Not Required : Defines path for http check : Defaults to root "/" path

haproxy_backend_servers : Required : Defines backend servers

      - {name: server1, ip: 192.168.1.10, port: 80}
      - {name: server2, ip: 192.168.1.11, port: 80}

haproxy_stats_users : Required : Defines user credentials for haproxy's web access : Defaults to 'username' 'password'

      - {username: username, password: password}

License
-------

MIT
