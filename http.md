# HTTP

HTTP (Hyper Text Transfer Protocol) is an Application Layer Protocol to exchange or transfer hypertext.

Spec: [RFC 2616](https://tools.ietf.org/html/rfc2616)


## URL Format:

```
http_URL = "http:" "//" host [ ":" port ] [ abs_path [ "?" query ]]
```

Example:
```
http://imagineer.in/hello
```

## Request Format

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

Example:
```
GET /hello HTTP/1.1
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
Accept-Encoding: gzip, deflate, sdch
Accept-Language: en-US,en;q=0.8,es;q=0.6,id;q=0.4,th;q=0.2,fr;q=0.2
Cache-Control: no-cache
Connection: keep-alive
Host: imagineer.in
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_11_6) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/52.0.2743.116 Safari/537.36
```

## Response Format

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

Example:

```
HTTP/1.1 404 Not Found
Connection: keep-alive
Content-Encoding: gzip
Content-Type: text/html
Date: Mon, 15 Aug 2016 21:25:55 GMT
ETag: W/"57a6407b-2b06"
Last-Modified: Sat, 06 Aug 2016 19:54:35 GMT
Server: nginx
Transfer-Encoding: chunked
Vary: Accept-Encoding

<html>
<head><title>404 Not Found</title></head>
<body bgcolor="white">
<center><h1>404 Not Found</h1></center>
<hr><center>nginx</center>
</body>
</html>
```

(**CR**: Carriage Return, **LF**: Line Feed, **SP**: Space)



### HTTP Headers

[List of http header fields](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields)


### Status Codes

<table>
    <thead>
        <tr>
            <th>Status Code</th>
            <th>Message</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td colspan="2"><strong>1xx Informational</strong></td>
        </tr>
        <tr>
            <td>100</td>
            <td>Continue</td>
        </tr>
        <tr>
            <td>101</td>
            <td>Switching Protocols</td>
        </tr>
        <tr>
            <td>102</td>
            <td>Processing</td>
        </tr>
        <tr>
            <td colspan="2"><strong>2xx Success</strong></td>
        </tr>
        <tr>
            <td>200</td>
            <td>OK</td>
        </tr>
        <tr>
            <td>201</td>
            <td>Created</td>
        </tr>
        <tr>
            <td>202</td>
            <td>Accepted</td>
        </tr>
        <tr>
            <td>203</td>
            <td>Non-Authoritative Information</td>
        </tr>
        <tr>
            <td>204</td>
            <td>No Content</td>
        </tr>
        <tr>
            <td>205</td>
            <td>Reset Content</td>
        </tr>
        <tr>
            <td>206</td>
            <td>Partial Content</td>
        </tr>
        <tr>
            <td colspan="2"><strong>3xx Redirection</strong></td>
        </tr>
        <tr>
            <td>300</td>
            <td>Multiple Choices</td>
        </tr>
        <tr>
            <td>301</td>
            <td>Moved Permanantly</td>
        </tr>
        <tr>
            <td>302</td>
            <td>Found</td>
        </tr>
        <tr>
            <td>303</td>
            <td>Multiple Choices</td>
        </tr>
        <tr>
            <td>304</td>
            <td>Not Modified</td>
        </tr>
        <tr>
            <td>305</td>
            <td>Use Proxy</td>
        </tr>
        <tr>
            <td>306</td>
            <td>(Unused)</td>
        </tr>
        <tr>
            <td>307</td>
            <td>Temporary Redirect</td>
        </tr>
        <tr>
            <td>308</td>
            <td>Permanent Redirect</td>
        </tr>
        <tr>
            <td colspan="2"><strong>4xx Client Error</strong></td>
        </tr>
        <tr>
            <td>400</td>
            <td>Bad Request</td>
        </tr>
        <tr>
            <td>401</td>
            <td>Unauthorized</td>
        </tr>
        <tr>
            <td>402</td>
            <td>Payment Required</td>
        </tr>
        <tr>
            <td>403</td>
            <td>Forbidden</td>
        </tr>
        <tr>
            <td>404</td>
            <td>Not Found</td>
        </tr>
        <tr>
            <td>405</td>
            <td>Method Not Allowed</td>
        </tr>
        <tr>
            <td>406</td>
            <td>Not Acceptable</td>
        </tr>
        <tr>
            <td>407</td>
            <td>Proxy Authentication Required</td>
        </tr>
        <tr>
            <td>408</td>
            <td>Request Timeout</td>
        </tr>
        <tr>
            <td>409</td>
            <td>Conflict</td>
        </tr>
        <tr>
            <td>410</td>
            <td>Gone</td>
        </tr>
        <tr>
            <td>411</td>
            <td>Length Required</td>
        </tr>
        <tr>
            <td>412</td>
            <td>Precondition Failed</td>
        </tr>
        <tr>
            <td>413</td>
            <td>Request Entity Too Large</td>
        </tr>
        <tr>
            <td>414</td>
            <td>Request-URI Too Long</td>
        </tr>
        <tr>
            <td>415</td>
            <td>Unsupported Media Type</td>
        </tr>
        <tr>
            <td>416</td>
            <td>Requested Range Not Satisfiable</td>
        </tr>
        <tr>
            <td>417</td>
            <td>Expectation Failed</td>
        </tr>
        <tr>
            <td>418</td>
            <td>I'm a teapot</td>
        </tr>
        <tr>
            <td>421</td>
            <td>Misdirected Request</td>
        </tr>
        <tr>
            <td>422</td>
            <td>Unprocessable Entity</td>
        </tr>
        <tr>
            <td>423</td>
            <td>Locked</td>
        </tr>
        <tr>
            <td>424</td>
            <td>Failed Dependency</td>
        </tr>
        <tr>
            <td>426</td>
            <td>Upgrade Required</td>
        </tr>
        <tr>
            <td>428</td>
            <td>Precondition Required</td>
        </tr>
        <tr>
            <td>429</td>
            <td>Too Many Requests</td>
        </tr>
        <tr>
            <td>431</td>
            <td>Request Header Fields Too Large</td>
        </tr>
        <tr>
            <td>444</td>
            <td>Connection Closed Without Response</td>
        </tr>
        <tr>
            <td>451</td>
            <td>Unavailable For Legal Reasons</td>
        </tr>
        <tr>
            <td>499</td>
            <td>Client Closed Request</td>
        </tr>
        <tr>
            <td colspan="2"><strong>5xx Server Error</strong></td>
        </tr>
        <tr>
            <td>500</td>
            <td>Internal Server Error</td>
        </tr>
        <tr>
            <td>501</td>
            <td>Not Implemented</td>
        </tr>
        <tr>
            <td>502</td>
            <td>Bad Gateway</td>
        </tr>
        <tr>
            <td>503</td>
            <td>Service Unavailable</td>
        </tr>
        <tr>
            <td>504</td>
            <td>Gateway Timeout</td>
        </tr>
        <tr>
            <td>505</td>
            <td>HTTP Version Not Supported</td>
        </tr>
        <tr>
            <td>506</td>
            <td>Variant Also Negotiates</td>
        </tr>
        <tr>
            <td>507</td>
            <td>Insufficient Storage</td>
        </tr>
        <tr>
            <td>508</td>
            <td>Loop Detected</td>
        </tr>
        <tr>
            <td>510</td>
            <td>Not Extended</td>
        </tr>
        <tr>
            <td>511</td>
            <td>Network Authentication Required</td>
        </tr>
        <tr>
            <td>599</td>
            <td>Network Connect Timeout Error</td>
        </tr>
    </tbody>
</table>

More info at [httpstatuses.com](https://httpstatuses.com/)


## More info:

- Specs:
  - HTTP/1.0 [RFC 1945](https://tools.ietf.org/html/rfc1945)
  - HTTP/1.1 [RFC 2616](https://tools.ietf.org/html/rfc2616)
  - HTTP/2 [RFC 7540](https://tools.ietf.org/html/rfc7540)
- [Evolution of HTTP - MDN](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Evolution_of_HTTP)
