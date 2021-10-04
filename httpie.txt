Httpie human friendly CLI
To learn more check: https://httpie.io/docs

Python plugins(Interesting):
- httpie-jwt-auth: https://github.com/teracyhq/httpie-jwt-auth

Basic command:
http [flags] [METHOD] URL [ITEM]

Sample Hello World:
https httpie.io/Hello

Result:
`

HTTP/1.1 200 OK
CF-Cache-Status: DYNAMIC
CF-RAY: 691e8b1169266c33-SIN
Connection: keep-alive
Content-Encoding: gzip
Content-Type: application/json; charset=utf-8
Date: Mon, 20 Sep 2021 22:38:20 GMT
Expect-CT: max-age=604800, report-uri="https://report-uri.cloudflare.com/cdn-cgi/beacon/expect-ct"
NEL: {"success_fraction":0,"report_to":"cf-nel","max_age":604800}
Report-To: {"endpoints":[{"url":"https:\/\/a.nel.cloudflare.com\/report\/v3?s=9Q04fRZBtyXnjxCOM2Nlaxyj%2BbpAsrk7Wc%2BSd%2Bb28A3JORiAEEd%2BH6MRVURGy%2BPK0Ve4nLTvCgNBgTkXIeGzoU5602Zw3Jywo67KRUctWbKIOssZ9GBkrl7joio%3D"}],"group":"cf-nel","max_age":604800}
Server: cloudflare
Transfer-Encoding: chunked
age: 0
alt-svc: h3=":443"; ma=86400, h3-29=":443"; ma=86400, h3-28=":443"; ma=86400, h3-27=":443"; ma=86400
cache-control: public, max-age=0, must-revalidate
etag: W/"105-tuZg7HTShsOZ9QXSZS0pqWYQ2Ac"
x-matched-path: /api/hello
x-vercel-cache: MISS
x-vercel-id: sin1::iad1::2v7jj-1632177497839-4b362b7c99e8

{
    "ahoy": [
        "Hello, World! 👋 Thank you for trying out HTTPie 🥳",
        "We hope this will become a friendship."
    ],
    "links": {
        "discord": "https://httpie.io/chat",
        "github": "https://github.com/httpie",
        "homepage": "https://httpie.io",
        "twitter": "https://twitter.com/httpie"
    }
}

`

To Add Headers specially Authorization:
http http://localhost:8062/admin/lesson-roadmap 'Authorization:Bearer [Token]'

Result:
`
HTTP/1.1 200 OK
Connection: keep-alive
Date: Mon, 20 Sep 2021 22:43:00 GMT
Keep-Alive: timeout=5
accept-ranges: bytes
access-control-allow-credentials: true
access-control-allow-headers: *
access-control-expose-headers: WWW-Authenticate,Server-Authorization
cache-control: no-cache
content-length: 112
content-type: application/json; charset=utf-8
vary: origin

{
    "Items": [
        {
            "id": "20211",
            "year": "2021"
        },
        {
            "id": "20212",
            "year": "2021"
        },
        {
            "id": "20216",
            "year": "2021"
        }
    ],
    "cursor": null
}
`

Sending JSON example:
http PUT pie.dev/put name=John email=john@example.org

Result:
`
PUT / HTTP/1.1
Accept: application/json, */*;q=0.5
Accept-Encoding: gzip, deflate
Content-Type: application/json
Host: pie.dev

{
    "name": "John",
    "email": "john@example.org"
}
`
