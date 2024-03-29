# rest_api_response_codes
sample standard response codes json. intended to use in REST API response generation. created based on RFC 2616. <a href="https://www.ietf.org/rfc/rfc2616.txt">refer here</a>


## Response Codes Structue

   The first digit of the Status-Code defines the class of response. The
   last two digits do not have any categorization role. There are 5
   values for the first digit:

      - 1xx: Informational - Request received, continuing process

      - 2xx: Success - The action was successfully received,
        understood, and accepted

      - 3xx: Redirection - Further action must be taken in order to
        complete the request

      - 4xx: Client Error - The request contains bad syntax or cannot
        be fulfilled

      - 5xx: Server Error - The server failed to fulfill an apparently
        valid request

   The individual values of the numeric status codes defined for
   HTTP/1.1, and an example set of corresponding Reason-Phrase's, are
   presented below. The reason phrases listed here are only
   recommendations -- they MAY be replaced by local equivalents without
   affecting the protocol.


```
        Status-Code    =  Description
          | "100"  ; Section 10.1.1: Continue
          | "101"  ; Section 10.1.2: Switching Protocols
          
          | "200"  ; Section 10.2.1: OK
          | "201"  ; Section 10.2.2: Created
          | "202"  ; Section 10.2.3: Accepted
          | "203"  ; Section 10.2.4: Non-Authoritative Information
          | "204"  ; Section 10.2.5: No Content
          | "205"  ; Section 10.2.6: Reset Content
          | "206"  ; Section 10.2.7: Partial Content
          
          | "300"  ; Section 10.3.1: Multiple Choices
          | "301"  ; Section 10.3.2: Moved Permanently
          | "302"  ; Section 10.3.3: Found
          | "303"  ; Section 10.3.4: See Other
          | "304"  ; Section 10.3.5: Not Modified
          | "305"  ; Section 10.3.6: Use Proxy
          | "307"  ; Section 10.3.8: Temporary Redirect
          
          | "400"  ; Section 10.4.1: Bad Request
          | "401"  ; Section 10.4.2: Unauthorized
          | "402"  ; Section 10.4.3: Payment Required
          | "403"  ; Section 10.4.4: Forbidden
          | "404"  ; Section 10.4.5: Not Found
          | "405"  ; Section 10.4.6: Method Not Allowed
          | "406"  ; Section 10.4.7: Not Acceptable
          | "407"  ; Section 10.4.8: Proxy Authentication Required
          | "408"  ; Section 10.4.9: Request Time-out
          | "409"  ; Section 10.4.10: Conflict
          | "410"  ; Section 10.4.11: Gone
          | "411"  ; Section 10.4.12: Length Required
          | "412"  ; Section 10.4.13: Precondition Failed
          | "413"  ; Section 10.4.14: Request Entity Too Large
          | "414"  ; Section 10.4.15: Request-URI Too Large
          | "415"  ; Section 10.4.16: Unsupported Media Type
          | "416"  ; Section 10.4.17: Requested range not satisfiable
          | "417"  ; Section 10.4.18: Expectation Failed
        
          | "500"  ; Section 10.5.1: Internal Server Error
          | "501"  ; Section 10.5.2: Not Implemented
          | "502"  ; Section 10.5.3: Bad Gateway
          | "503"  ; Section 10.5.4: Service Unavailable
          | "504"  ; Section 10.5.5: Gateway Time-out
          | "505"  ; Section 10.5.6: HTTP Version not supported

```

Note: Section Refers to chapter in rfc2616 Doc. <a href="https://www.ietf.org/rfc/rfc2616.txt">click here</a>.

Sample Format of REST API Response codes JSON :
```
"200":{
        "_id":"200",
        "status_code":"200",
        "message":"success",
        "desc":"request acceppted successfully"
    }
```

## custom response codes preparation:

The main intention for creating these custom response codes are to eliminate the creating frequently using REST API Regular Responses/response errors [like invalid parameters ...] for every time.

custom response codes will be 4-digits for below reasons:

  1. for differentiating standard HTTP/1.1 codes and our custom response codes.

        a. The first digit of the Status-Code defines the class of response[same as HTTP/1.1].

        b. The first 3-digits are HTTP/1.1 response codes and our custom response under that category         only.   


```
      Status-Code      Message                  Description
          | "2011"  ;  Data Deleted             data/record(s) deleted successfully 
          | "2012"  ;  Data Updated             data/record(s) updated successfully 
        
          | "2022"  ;  Rejected                 Request Rejected
          
          | "4001"  ;  Invalid Parameters       Invalid Parameters
          | "4002"  ;  Invalid Payload          Invalid body or payload data


          | "4011"  ;  Invalid Headers          Headers Missing or invalid Headers. Required headers not supplied
          | "4012"  ;  Invalid Auth Token       Auth Token/bearer token Missing. Required Auth Token is not supplied
          | "4013"  ;  Invalid Credetials       Invalid credetials. username or password not matched to our records
```

