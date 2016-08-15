##HTTP

Spec: [RFC 2616](https://www.w3.org/Protocols/rfc2616/rfc2616.html)

###URL Format:

```
http_URL = "http:" "//" host [ ":" port ] [ abs_path [ "?" query ]]
```

###Request Format

HTTP request in BNF

```
Request          = Request-Line
                    *(( general-header
                     | request-header
                     | entity-header ) CRLF)
                     CRLF
                     [ message-body ]


Request-Line     = Method SP Request-URI SP HTTP-Version CRLF

Method           = "GET" | "HEAD" | "POST" | "PUT" | "DELETE"
                    | "OPTIONS" | "TRACE" | "CONNECT"
                    | extension-method
extension-method = token

Request-URI      = "*" | absoluteURI | abs_path | authority

HTTP-Version     = "HTTP" "/" 1*DIGIT "." 1*DIGIT

general-header   = Cache-Control
                      | Connection
                      | Date
                      | Pragma
                      | Trailer
                      | Transfer-Encoding
                      | Upgrade
                      | Via
                      | Warning
request-header   = Accept
                      | Accept-Charset
                      | Accept-Encoding
                      | Accept-Language
                      | Authorization
                      | Expect
                      | From
                      | Host
                      | If-Match
                      | If-Modified-Since
                      | If-None-Match
                      | If-Range
                      | If-Unmodified-Since
                      | Max-Forwards
                      | Proxy-Authorization
                      | Range
                      | Referer
                      | TE
                      | User-Agent
entity-header    = Allow
                      | Content-Encoding
                      | Content-Language
                      | Content-Length
                      | Content-Location
                      | Content-MD5
                      | Content-Range
                      | Content-Type
                      | Expires
                      | Last-Modified
                      | extension-header
extension-header = message-header

message-body     = entity-body
                    | <entity-body encoded as per Transfer-Encoding>
```

###Response Format

HTTP response in BNF:

```
Response            = Status-Line
                       *(( general-header
                        | response-header
                        | entity-header ) CRLF)
                       CRLF
                       [ message-body ]
Status-Line         = HTTP-Version SP Status-Code SP Reason-Phrase CRLF

Status-Code         = "100" | "101"
                      | "200" | "201" | "202" | "203" | "204" | "205" | "206"
                      | "300" | "301" | "302" | "303" | "304" | "305" | "307"
                      | "400" | "401" | "402" | "403" | "404" | "405" | "406"
                      | "407" | "408" | "409" | "410" | "411" | "412" | "413"
                      | "414" | "415" | "416" | "417"
                      | "500" | "501" | "502" | "503" | "504" | "505"
                      | extension-code
extension-code      = 3DIGIT
Reason-Phrase       = *<TEXT, excluding CR, LF>

response-header     = Accept-Ranges
                       | Age
                       | ETag
                       | Location
                       | Proxy-Authenticate
                       | Retry-After
                       | Server
                       | Vary
                       | WWW-Authenticate
```
