# Instructions

- Following Playwright test failed.
- Explain why, be concise, respect Playwright best practices.
- Provide a snippet of code with the fix, if possible.

# Test info

- Name: ui/auth/signup.spec.ts >> Signup >> rejects signup with an already-registered email @regression
- Location: tests/ui/auth/signup.spec.ts:30:3

# Error details

```
Error: apiRequestContext.post: Max redirect count exceeded
Call log:
  - → POST https://automationexercise.com/api/createAccount
    - user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.5 Safari/605.1.15
    - accept: */*
    - accept-encoding: gzip,deflate,br
    - content-type: application/x-www-form-urlencoded
    - content-length: 340
  - ← 302 Found
    - date: Fri, 03 Jul 2026 22:00:51 GMT
    - content-type: text/html; charset=utf-8
    - transfer-encoding: chunked
    - connection: keep-alive
    - referrer-policy: same-origin
    - x-frame-options: DENY
    - x-content-type-options: nosniff
    - x-powered-by: Phusion Passenger(R) 6.1.2
    - location: /
    - status: 302 Found
    - server: cloudflare
    - cf-cache-status: DYNAMIC
    - report-to: {"group":"cf-nel","max_age":604800,"endpoints":[{"url":"https://a.nel.cloudflare.com/report/v4?s=pt2%2F00qKqUgd%2FMzC99ZFr0fLkKUIhDZbnq4zZkWVsue%2BL7Sy5hRWz%2FHWoxkFhbYbc0bmi%2BZC3xWG8Y1B5djG%2FACgDgurNq03txLzN9fMr6smRcLw1fCkItWW9ENQ8fj72lMLySUwXjcP"}]}
    - nel: {"report_to":"cf-nel","success_fraction":0.0,"max_age":604800}
    - cf-ray: a1592a5b5c383bd1-IAD
    - alt-svc: h3=":443"; ma=86400
  - → GET https://automationexercise.com/
    - user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.5 Safari/605.1.15
    - accept: */*
    - accept-encoding: gzip,deflate,br
  - ← 302 Found
    - date: Fri, 03 Jul 2026 22:00:52 GMT
    - content-type: text/html; charset=utf-8
    - transfer-encoding: chunked
    - connection: keep-alive
    - referrer-policy: same-origin
    - x-frame-options: DENY
    - x-content-type-options: nosniff
    - x-powered-by: Phusion Passenger(R) 6.1.2
    - location: /
    - status: 302 Found
    - server: cloudflare
    - cf-cache-status: DYNAMIC
    - report-to: {"group":"cf-nel","max_age":604800,"endpoints":[{"url":"https://a.nel.cloudflare.com/report/v4?s=NN8sorZxwvFXUUEMfM%2Fy7Y9HOJm0HHL982nhT2LQMIWlbaoA00AK4%2BIYEJk67%2Fnd%2FmvsSVvsbTcavii4D6hbVX64QfcXkMg%2FCD0Fc0o%2FC%2F%2Bu%2FtBmQ4M4J%2BNJekr7eKVTNcNkzX0fnwVF"}]}
    - nel: {"report_to":"cf-nel","success_fraction":0.0,"max_age":604800}
    - cf-ray: a1592a5dc9d614bc-IAD
    - alt-svc: h3=":443"; ma=86400
  - → GET https://automationexercise.com/
    - user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.5 Safari/605.1.15
    - accept: */*
    - accept-encoding: gzip,deflate,br
  - ← 302 Found
    - date: Fri, 03 Jul 2026 22:00:52 GMT
    - content-type: text/html; charset=utf-8
    - transfer-encoding: chunked
    - connection: keep-alive
    - referrer-policy: same-origin
    - x-frame-options: DENY
    - x-content-type-options: nosniff
    - x-powered-by: Phusion Passenger(R) 6.1.2
    - location: /
    - status: 302 Found
    - server: cloudflare
    - cf-cache-status: DYNAMIC
    - report-to: {"group":"cf-nel","max_age":604800,"endpoints":[{"url":"https://a.nel.cloudflare.com/report/v4?s=bDpymB0nZEhHp%2FvYDFji38ZeYcJT4zb%2B5rF0AVMjn3rGckGDtbddmHAnWedZLMZDDH2LbF75NM1ZPiJorUdCAGYoLrayF8dc5THlgqQ1Bnhho2QwtV8Y3HWfBBUwMr9d0tvJvDRySr3s"}]}
    - nel: {"report_to":"cf-nel","success_fraction":0.0,"max_age":604800}
    - cf-ray: a1592a603c18290e-IAD
    - alt-svc: h3=":443"; ma=86400
  - → GET https://automationexercise.com/
    - user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.5 Safari/605.1.15
    - accept: */*
    - accept-encoding: gzip,deflate,br
  - ← 302 Found
    - date: Fri, 03 Jul 2026 22:00:52 GMT
    - content-type: text/html; charset=utf-8
    - transfer-encoding: chunked
    - connection: keep-alive
    - referrer-policy: same-origin
    - x-frame-options: DENY
    - x-content-type-options: nosniff
    - x-powered-by: Phusion Passenger(R) 6.1.2
    - location: /
    - status: 302 Found
    - server: cloudflare
    - cf-cache-status: DYNAMIC
    - report-to: {"group":"cf-nel","max_age":604800,"endpoints":[{"url":"https://a.nel.cloudflare.com/report/v4?s=hZ7b%2FhhfabQTHulB4RhUNji3JKQfY5tqaJg%2FM8wArgYX9tXT0k%2B2gmIOfn6wnqlvXQoWv8StrAaikUJJdNin1yKe64PcX6FwpSMm560w%2BVZwsyrXRUoBw1EMBtITzrNFRztnaMq1atkg"}]}
    - nel: {"report_to":"cf-nel","success_fraction":0.0,"max_age":604800}
    - cf-ray: a1592a62bd077d17-IAD
    - alt-svc: h3=":443"; ma=86400
  - → GET https://automationexercise.com/
    - user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.5 Safari/605.1.15
    - accept: */*
    - accept-encoding: gzip,deflate,br
  - ← 302 Found
    - date: Fri, 03 Jul 2026 22:00:53 GMT
    - content-type: text/html; charset=utf-8
    - transfer-encoding: chunked
    - connection: keep-alive
    - referrer-policy: same-origin
    - x-frame-options: DENY
    - x-content-type-options: nosniff
    - x-powered-by: Phusion Passenger(R) 6.1.2
    - location: /
    - status: 302 Found
    - server: cloudflare
    - cf-cache-status: DYNAMIC
    - report-to: {"group":"cf-nel","max_age":604800,"endpoints":[{"url":"https://a.nel.cloudflare.com/report/v4?s=AAJVusZ4gDLu6NaqX1r7tlQ1cXW7CAGVGInUdcmUP4LSgrUTcWTA0ubCc%2BIN0G3xyIBbtOvIu2orHQQ99Sj7eRu%2F0U3rZLDs4yQewmMOlifNcLDUO3HwEL4bvaxfghxFjNHOSiD5EVqY"}]}
    - nel: {"report_to":"cf-nel","success_fraction":0.0,"max_age":604800}
    - cf-ray: a1592a652a53389d-IAD
    - alt-svc: h3=":443"; ma=86400
  - → GET https://automationexercise.com/
    - user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.5 Safari/605.1.15
    - accept: */*
    - accept-encoding: gzip,deflate,br
  - ← 302 Found
    - date: Fri, 03 Jul 2026 22:00:53 GMT
    - content-type: text/html; charset=utf-8
    - transfer-encoding: chunked
    - connection: keep-alive
    - referrer-policy: same-origin
    - x-frame-options: DENY
    - x-content-type-options: nosniff
    - x-powered-by: Phusion Passenger(R) 6.1.2
    - location: /
    - status: 302 Found
    - server: cloudflare
    - cf-cache-status: DYNAMIC
    - report-to: {"group":"cf-nel","max_age":604800,"endpoints":[{"url":"https://a.nel.cloudflare.com/report/v4?s=AeSFG%2BgP08PX44oRu5MXN%2FQLIF4s%2BOvRgp%2FOPxT%2BRSCWI%2BirWG94WAzRNKhirIZ5JTWdPg5saz%2FBqO%2Bkk%2BarnioWiC7v9Rvq1xy0e2E5sMVXO3xNMtbIRIoKfi8%2F0P8C2FwYMKsxLuCL"}]}
    - nel: {"report_to":"cf-nel","success_fraction":0.0,"max_age":604800}
    - cf-ray: a1592a68bc1e6060-IAD
    - alt-svc: h3=":443"; ma=86400
  - → GET https://automationexercise.com/
    - user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.5 Safari/605.1.15
    - accept: */*
    - accept-encoding: gzip,deflate,br
  - ← 302 Found
    - date: Fri, 03 Jul 2026 22:00:54 GMT
    - content-type: text/html; charset=utf-8
    - transfer-encoding: chunked
    - connection: keep-alive
    - referrer-policy: same-origin
    - x-frame-options: DENY
    - x-content-type-options: nosniff
    - x-powered-by: Phusion Passenger(R) 6.1.2
    - location: /
    - status: 302 Found
    - server: cloudflare
    - cf-cache-status: DYNAMIC
    - report-to: {"group":"cf-nel","max_age":604800,"endpoints":[{"url":"https://a.nel.cloudflare.com/report/v4?s=jvQhEdoUbc3vcKko7axxgPdoBPHi8lB2Zr5Tx88oxdfEhoeQacoR2ZFGzrHt51cZ7ARiarSHdk8QzeInPv2rChqw2yGnmtO9uwF6%2BTBo3ktz2o2pvptrjU827C0HZl4CfQjN5jUcFDoL"}]}
    - nel: {"report_to":"cf-nel","success_fraction":0.0,"max_age":604800}
    - cf-ray: a1592a6b1ce7c792-IAD
    - alt-svc: h3=":443"; ma=86400
  - → GET https://automationexercise.com/
    - user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.5 Safari/605.1.15
    - accept: */*
    - accept-encoding: gzip,deflate,br
  - ← 302 Found
    - date: Fri, 03 Jul 2026 22:00:54 GMT
    - content-type: text/html; charset=utf-8
    - transfer-encoding: chunked
    - connection: keep-alive
    - referrer-policy: same-origin
    - x-frame-options: DENY
    - x-content-type-options: nosniff
    - x-powered-by: Phusion Passenger(R) 6.1.2
    - location: /
    - status: 302 Found
    - server: cloudflare
    - cf-cache-status: DYNAMIC
    - report-to: {"group":"cf-nel","max_age":604800,"endpoints":[{"url":"https://a.nel.cloudflare.com/report/v4?s=oEgQvzV%2B6rKlG7T5jAw4lnGXxn7JiXZAfNKt81E%2F5YiokRLIW86xIeZswzFr4PzZJ5IoH0QNiYtV719Qf6cUnjkoKYC%2BIet8LjRE8%2FJG0V537r%2FSoHrOCQj%2BnA19m7xxP%2FC1FBiCEcpv"}]}
    - nel: {"report_to":"cf-nel","success_fraction":0.0,"max_age":604800}
    - cf-ray: a1592a6d991514f4-IAD
    - alt-svc: h3=":443"; ma=86400
  - → GET https://automationexercise.com/
    - user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.5 Safari/605.1.15
    - accept: */*
    - accept-encoding: gzip,deflate,br
  - ← 302 Found
    - date: Fri, 03 Jul 2026 22:00:55 GMT
    - content-type: text/html; charset=utf-8
    - transfer-encoding: chunked
    - connection: keep-alive
    - referrer-policy: same-origin
    - x-frame-options: DENY
    - x-content-type-options: nosniff
    - x-powered-by: Phusion Passenger(R) 6.1.2
    - location: /
    - status: 302 Found
    - server: cloudflare
    - cf-cache-status: DYNAMIC
    - report-to: {"group":"cf-nel","max_age":604800,"endpoints":[{"url":"https://a.nel.cloudflare.com/report/v4?s=32CNntvJo5lJgZy38qQuhBLE6LkqfNA7LB0bLWnirwGaDIGy4%2FbJ5JrhJzESzuD3kTTjzfLABJUEssp5rIaFowUa5CbwybDBdEB%2F0eon%2FqxPpm9T%2FBZGEAT1cfwTcBEhPFYggtjqMj2N"}]}
    - nel: {"report_to":"cf-nel","success_fraction":0.0,"max_age":604800}
    - cf-ray: a1592a7009b91729-IAD
    - alt-svc: h3=":443"; ma=86400
  - → GET https://automationexercise.com/
    - user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.5 Safari/605.1.15
    - accept: */*
    - accept-encoding: gzip,deflate,br
  - ← 302 Found
    - date: Fri, 03 Jul 2026 22:00:55 GMT
    - content-type: text/html; charset=utf-8
    - transfer-encoding: chunked
    - connection: keep-alive
    - referrer-policy: same-origin
    - x-frame-options: DENY
    - x-content-type-options: nosniff
    - x-powered-by: Phusion Passenger(R) 6.1.2
    - location: /
    - status: 302 Found
    - server: cloudflare
    - cf-cache-status: DYNAMIC
    - report-to: {"group":"cf-nel","max_age":604800,"endpoints":[{"url":"https://a.nel.cloudflare.com/report/v4?s=raZobW6QzZhXO8p%2BzINrxxKV1gquZQVWS3ZRaLNi5lfhAlQmclOkI2NL0wkl6c%2FoWfZQ1aTFrZ9TOFSmILKp%2Fl7v%2FR85C6YUYxtJl7TIUG3Ln7Pvqk6EUFOrcHCXJ9SDMSIOCqhvLOel"}]}
    - nel: {"report_to":"cf-nel","success_fraction":0.0,"max_age":604800}
    - cf-ray: a1592a729a45d8c1-IAD
    - alt-svc: h3=":443"; ma=86400
  - → GET https://automationexercise.com/
    - user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.5 Safari/605.1.15
    - accept: */*
    - accept-encoding: gzip,deflate,br
  - ← 302 Found
    - date: Fri, 03 Jul 2026 22:00:55 GMT
    - content-type: text/html; charset=utf-8
    - transfer-encoding: chunked
    - connection: keep-alive
    - referrer-policy: same-origin
    - x-frame-options: DENY
    - x-content-type-options: nosniff
    - x-powered-by: Phusion Passenger(R) 6.1.2
    - location: /
    - status: 302 Found
    - server: cloudflare
    - cf-cache-status: DYNAMIC
    - report-to: {"group":"cf-nel","max_age":604800,"endpoints":[{"url":"https://a.nel.cloudflare.com/report/v4?s=G3mUBsCKoIGB9%2BO4CuWxvmPB3mW%2F9GBr4sAuidPubEnf8%2BwLYINWZuhW2P5OfRq33oFClw0%2FHOh4dbCPzE%2FAb9Zn22WDE03vrERgNP%2FdaH%2FfguqFy8BFYPFOqQTjBO6yrDI9tEvlQ2Wo"}]}
    - nel: {"report_to":"cf-nel","success_fraction":0.0,"max_age":604800}
    - cf-ray: a1592a753bcfe5f9-IAD
    - alt-svc: h3=":443"; ma=86400
  - → GET https://automationexercise.com/
    - user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.5 Safari/605.1.15
    - accept: */*
    - accept-encoding: gzip,deflate,br
  - ← 302 Found
    - date: Fri, 03 Jul 2026 22:00:56 GMT
    - content-type: text/html; charset=utf-8
    - transfer-encoding: chunked
    - connection: keep-alive
    - referrer-policy: same-origin
    - x-frame-options: DENY
    - x-content-type-options: nosniff
    - x-powered-by: Phusion Passenger(R) 6.1.2
    - location: /
    - status: 302 Found
    - server: cloudflare
    - cf-cache-status: DYNAMIC
    - report-to: {"group":"cf-nel","max_age":604800,"endpoints":[{"url":"https://a.nel.cloudflare.com/report/v4?s=rVg5RVC%2FLWHsV2oG7MWncpfxEADhO6IkX3DC6HuTC0A2Ytq6I3B%2F3HD9d9FW5bEfqFS6Jo4ZZULunCfeDhi1VosUIuCe14dzuRY5Xv3QF9use4baOz84PouB0%2FRbyXzLShPbBAjgCqhr"}]}
    - nel: {"report_to":"cf-nel","success_fraction":0.0,"max_age":604800}
    - cf-ray: a1592a77aad29c46-IAD
    - alt-svc: h3=":443"; ma=86400
  - → GET https://automationexercise.com/
    - user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.5 Safari/605.1.15
    - accept: */*
    - accept-encoding: gzip,deflate,br
  - ← 302 Found
    - date: Fri, 03 Jul 2026 22:00:56 GMT
    - content-type: text/html; charset=utf-8
    - transfer-encoding: chunked
    - connection: keep-alive
    - referrer-policy: same-origin
    - x-frame-options: DENY
    - x-content-type-options: nosniff
    - x-powered-by: Phusion Passenger(R) 6.1.2
    - location: /
    - status: 302 Found
    - server: cloudflare
    - cf-cache-status: DYNAMIC
    - report-to: {"group":"cf-nel","max_age":604800,"endpoints":[{"url":"https://a.nel.cloudflare.com/report/v4?s=9U9fxCrlFJsCNXC0myxhuwt0W0iEGnEz5epxAxEefFajHC4PfL7yHO8e6PkwADntGfwq2HYCSw4D%2F%2F0%2Fa7BirO54k%2Bh8kerHEZYPPyRkmxqu0sNGnHOeDhNkinDP3pOo6AZbCMwS1gsI"}]}
    - nel: {"report_to":"cf-nel","success_fraction":0.0,"max_age":604800}
    - cf-ray: a1592a7a2d8d3f01-IAD
    - alt-svc: h3=":443"; ma=86400
  - → GET https://automationexercise.com/
    - user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.5 Safari/605.1.15
    - accept: */*
    - accept-encoding: gzip,deflate,br
  - ← 302 Found
    - date: Fri, 03 Jul 2026 22:00:57 GMT
    - content-type: text/html; charset=utf-8
    - transfer-encoding: chunked
    - connection: keep-alive
    - referrer-policy: same-origin
    - x-frame-options: DENY
    - x-content-type-options: nosniff
    - x-powered-by: Phusion Passenger(R) 6.1.2
    - location: /
    - status: 302 Found
    - server: cloudflare
    - cf-cache-status: DYNAMIC
    - report-to: {"group":"cf-nel","max_age":604800,"endpoints":[{"url":"https://a.nel.cloudflare.com/report/v4?s=lIwnh%2B3oy67sx58WX1MaPwwi%2B6eI6lamROaBtHKaesr4AahF45Vuk7%2B4moPH3mh2nlGgKKR82BN%2BBxS%2B76akvA25J8AwSOI8%2Bez%2FaRcJD%2Boo%2Fq74wDW7788XqbhecF0Cw9qMWWMRJw9Z"}]}
    - nel: {"report_to":"cf-nel","success_fraction":0.0,"max_age":604800}
    - cf-ray: a1592a7ca806d6a5-IAD
    - alt-svc: h3=":443"; ma=86400
  - → GET https://automationexercise.com/
    - user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.5 Safari/605.1.15
    - accept: */*
    - accept-encoding: gzip,deflate,br
  - ← 302 Found
    - date: Fri, 03 Jul 2026 22:00:57 GMT
    - content-type: text/html; charset=utf-8
    - transfer-encoding: chunked
    - connection: keep-alive
    - referrer-policy: same-origin
    - x-frame-options: DENY
    - x-content-type-options: nosniff
    - x-powered-by: Phusion Passenger(R) 6.1.2
    - location: /
    - status: 302 Found
    - server: cloudflare
    - cf-cache-status: DYNAMIC
    - report-to: {"group":"cf-nel","max_age":604800,"endpoints":[{"url":"https://a.nel.cloudflare.com/report/v4?s=tzhSL%2BeRNdtKPedrgXHOgq%2FC4ToKnOQ50B2GY2RIEcKNZG5qlQ6qLGVnAp0uW31u5O%2FyR10aW01jmKD2XpeeVtjy4k%2FT87z5e%2BVhDJouYs3L%2FCqbQN%2B7omJXwIWkFm3ehsd5Ai2CliR0"}]}
    - nel: {"report_to":"cf-nel","success_fraction":0.0,"max_age":604800}
    - cf-ray: a1592a7f2c399307-IAD
    - alt-svc: h3=":443"; ma=86400
  - → GET https://automationexercise.com/
    - user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.5 Safari/605.1.15
    - accept: */*
    - accept-encoding: gzip,deflate,br
  - ← 302 Found
    - date: Fri, 03 Jul 2026 22:00:57 GMT
    - content-type: text/html; charset=utf-8
    - transfer-encoding: chunked
    - connection: keep-alive
    - referrer-policy: same-origin
    - x-frame-options: DENY
    - x-content-type-options: nosniff
    - x-powered-by: Phusion Passenger(R) 6.1.2
    - location: /
    - status: 302 Found
    - server: cloudflare
    - cf-cache-status: DYNAMIC
    - report-to: {"group":"cf-nel","max_age":604800,"endpoints":[{"url":"https://a.nel.cloudflare.com/report/v4?s=wjw%2F1mD%2BC4F%2BxNNtCKXsGxQ8fMY%2FeiCC1vPyar9QKRVyoQC9sF8mmLAY4%2BRgEMEApzuETtDuAh8pCpljJH3QRIXHPCqZNT6jHTpk338x3kc6QWarLRVkxaw7CIW9NAaPqKfnZe2Owcns"}]}
    - nel: {"report_to":"cf-nel","success_fraction":0.0,"max_age":604800}
    - cf-ray: a1592a818a9614bc-IAD
    - alt-svc: h3=":443"; ma=86400
  - → GET https://automationexercise.com/
    - user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.5 Safari/605.1.15
    - accept: */*
    - accept-encoding: gzip,deflate,br
  - ← 302 Found
    - date: Fri, 03 Jul 2026 22:00:58 GMT
    - content-type: text/html; charset=utf-8
    - transfer-encoding: chunked
    - connection: keep-alive
    - referrer-policy: same-origin
    - x-frame-options: DENY
    - x-content-type-options: nosniff
    - x-powered-by: Phusion Passenger(R) 6.1.2
    - location: /
    - status: 302 Found
    - server: cloudflare
    - cf-cache-status: DYNAMIC
    - report-to: {"group":"cf-nel","max_age":604800,"endpoints":[{"url":"https://a.nel.cloudflare.com/report/v4?s=15%2BdzoOzVTwuZ8OsVizxhBIBkvzSpLm4VJtnnAmSFhB21Vt6Iz2bSwIua91PaaujZ2Lifpsdj4Q8P6uK2veC6AXYr4uXOvli18tU3pOTvVB5LfIETE1gccMRjzf%2B6dLdoi3ftIwtNqW9"}]}
    - nel: {"report_to":"cf-nel","success_fraction":0.0,"max_age":604800}
    - cf-ray: a1592a840ee5e5ed-IAD
    - alt-svc: h3=":443"; ma=86400
  - → GET https://automationexercise.com/
    - user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.5 Safari/605.1.15
    - accept: */*
    - accept-encoding: gzip,deflate,br
  - ← 302 Found
    - date: Fri, 03 Jul 2026 22:00:58 GMT
    - content-type: text/html; charset=utf-8
    - transfer-encoding: chunked
    - connection: keep-alive
    - referrer-policy: same-origin
    - x-frame-options: DENY
    - x-content-type-options: nosniff
    - x-powered-by: Phusion Passenger(R) 6.1.2
    - location: /
    - status: 302 Found
    - server: cloudflare
    - cf-cache-status: DYNAMIC
    - report-to: {"group":"cf-nel","max_age":604800,"endpoints":[{"url":"https://a.nel.cloudflare.com/report/v4?s=9kM5q81uYYY8JiyhBgargS7T5vQyKidwwrjOIa0%2B8YrreU7s3Bn5FW6BM9sjhg2%2FBrFEGRCazJAiuKF2036MSHJbGYKvHS6lrVMl45%2FvmEiEAM2khnhwA1PA5%2BHje9IBj%2BQoAhBMMNYh"}]}
    - nel: {"report_to":"cf-nel","success_fraction":0.0,"max_age":604800}
    - cf-ray: a1592a867e6befaa-IAD
    - alt-svc: h3=":443"; ma=86400
  - → GET https://automationexercise.com/
    - user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.5 Safari/605.1.15
    - accept: */*
    - accept-encoding: gzip,deflate,br
  - ← 302 Found
    - date: Fri, 03 Jul 2026 22:00:59 GMT
    - content-type: text/html; charset=utf-8
    - transfer-encoding: chunked
    - connection: keep-alive
    - referrer-policy: same-origin
    - x-frame-options: DENY
    - x-content-type-options: nosniff
    - x-powered-by: Phusion Passenger(R) 6.1.2
    - location: /
    - status: 302 Found
    - server: cloudflare
    - cf-cache-status: DYNAMIC
    - report-to: {"group":"cf-nel","max_age":604800,"endpoints":[{"url":"https://a.nel.cloudflare.com/report/v4?s=V1ts8tehiqsphpvHLuhvqR4hrPi%2FgrFDX2HqjHu5dTUe39sx0QeC2MX4k6Z8zyBNQtWiXdvFdVqeQze%2FOGefP7PEbRemLlwhiCugGUKF6qY4%2F6PU3uaeV73L42q5cs%2BRDhdR2ht9cQgy"}]}
    - nel: {"report_to":"cf-nel","success_fraction":0.0,"max_age":604800}
    - cf-ray: a1592a88fb757d17-IAD
    - alt-svc: h3=":443"; ma=86400
  - → GET https://automationexercise.com/
    - user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.5 Safari/605.1.15
    - accept: */*
    - accept-encoding: gzip,deflate,br
  - ← 302 Found
    - date: Fri, 03 Jul 2026 22:00:59 GMT
    - content-type: text/html; charset=utf-8
    - transfer-encoding: chunked
    - connection: keep-alive
    - referrer-policy: same-origin
    - x-frame-options: DENY
    - x-content-type-options: nosniff
    - x-powered-by: Phusion Passenger(R) 6.1.2
    - location: /
    - status: 302 Found
    - server: cloudflare
    - cf-cache-status: DYNAMIC
    - report-to: {"group":"cf-nel","max_age":604800,"endpoints":[{"url":"https://a.nel.cloudflare.com/report/v4?s=bNsKhkSy5m11GKDGKNVVNFHg%2F44zKlQJNTbvA1Zov3AGmIg37448pGxAX%2BKCHUfw2DG8ilJY0mHaO3RN62mfMB8TyFBiV0DHflYq6WvFOHMKf3JbLVhFT5L0%2BRfShsG4QaXXDtI6%2BLBf"}]}
    - nel: {"report_to":"cf-nel","success_fraction":0.0,"max_age":604800}
    - cf-ray: a1592a8b6e438c22-IAD
    - alt-svc: h3=":443"; ma=86400
  - → GET https://automationexercise.com/
    - user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.5 Safari/605.1.15
    - accept: */*
    - accept-encoding: gzip,deflate,br
  - ← 302 Found
    - date: Fri, 03 Jul 2026 22:00:59 GMT
    - content-type: text/html; charset=utf-8
    - transfer-encoding: chunked
    - connection: keep-alive
    - referrer-policy: same-origin
    - x-frame-options: DENY
    - x-content-type-options: nosniff
    - x-powered-by: Phusion Passenger(R) 6.1.2
    - location: /
    - status: 302 Found
    - server: cloudflare
    - cf-cache-status: DYNAMIC
    - report-to: {"group":"cf-nel","max_age":604800,"endpoints":[{"url":"https://a.nel.cloudflare.com/report/v4?s=njEJA4GjtTwldvUd3jUr6FtutwvYukoORWq8kdSWlU%2FlChXJQamMYNWabdATkCSvfLxqzSDxo5hPH3EKqlcqK%2Bb7EJbfAhU%2FjVif%2FRkuwtvwJofdS5F8slDq1P9uPwdJKjfyeT3FBudc"}]}
    - nel: {"report_to":"cf-nel","success_fraction":0.0,"max_age":604800}
    - cf-ray: a1592a8dea72a13a-IAD
    - alt-svc: h3=":443"; ma=86400

```

# Test source

```ts
  1  | import type { APIRequestContext, APIResponse } from '@playwright/test';
  2  | import { endpoints } from './endpoints';
  3  | import type { User } from './models/user.model';
  4  | 
  5  | function userToForm(user: User): Record<string, string> {
  6  |   return {
  7  |     name: user.name,
  8  |     email: user.email,
  9  |     password: user.password,
  10 |     title: user.title,
  11 |     birth_date: user.birthDate,
  12 |     birth_month: user.birthMonth,
  13 |     birth_year: user.birthYear,
  14 |     firstname: user.firstName,
  15 |     lastname: user.lastName,
  16 |     company: user.company,
  17 |     address1: user.address1,
  18 |     address2: user.address2,
  19 |     country: user.country,
  20 |     zipcode: user.zipcode,
  21 |     state: user.state,
  22 |     city: user.city,
  23 |     mobile_number: user.mobileNumber,
  24 |   };
  25 | }
  26 | 
  27 | export class ApiClient {
  28 |   constructor(private readonly request: APIRequestContext) {}
  29 | 
  30 |   getProductsList(): Promise<APIResponse> {
  31 |     return this.request.get(endpoints.productsList);
  32 |   }
  33 | 
  34 |   postProductsList(): Promise<APIResponse> {
  35 |     return this.request.post(endpoints.productsList);
  36 |   }
  37 | 
  38 |   getBrandsList(): Promise<APIResponse> {
  39 |     return this.request.get(endpoints.brandsList);
  40 |   }
  41 | 
  42 |   putBrandsList(): Promise<APIResponse> {
  43 |     return this.request.put(endpoints.brandsList);
  44 |   }
  45 | 
  46 |   searchProduct(searchTerm: string): Promise<APIResponse> {
  47 |     return this.request.post(endpoints.searchProduct, { form: { search_product: searchTerm } });
  48 |   }
  49 | 
  50 |   searchProductMissingParam(): Promise<APIResponse> {
  51 |     return this.request.post(endpoints.searchProduct);
  52 |   }
  53 | 
  54 |   verifyLogin(email: string, password: string): Promise<APIResponse> {
  55 |     return this.request.post(endpoints.verifyLogin, { form: { email, password } });
  56 |   }
  57 | 
  58 |   verifyLoginMissingParam(email: string): Promise<APIResponse> {
  59 |     return this.request.post(endpoints.verifyLogin, { form: { email } });
  60 |   }
  61 | 
  62 |   deleteVerifyLogin(): Promise<APIResponse> {
  63 |     return this.request.delete(endpoints.verifyLogin);
  64 |   }
  65 | 
  66 |   createAccount(user: User): Promise<APIResponse> {
> 67 |     return this.request.post(endpoints.createAccount, { form: userToForm(user) });
     |                         ^ Error: apiRequestContext.post: Max redirect count exceeded
  68 |   }
  69 | 
  70 |   updateAccount(user: User): Promise<APIResponse> {
  71 |     return this.request.put(endpoints.updateAccount, { form: userToForm(user) });
  72 |   }
  73 | 
  74 |   deleteAccount(email: string, password: string): Promise<APIResponse> {
  75 |     return this.request.delete(endpoints.deleteAccount, { form: { email, password } });
  76 |   }
  77 | 
  78 |   getUserDetailByEmail(email: string): Promise<APIResponse> {
  79 |     return this.request.get(endpoints.getUserDetailByEmail, { params: { email } });
  80 |   }
  81 | }
  82 | 
```