# cHail

Simulates parallel access to URLs through a configurable number of clients

## Usage

        Usage: chail [options...]> <url>...
        Options:
        -H value
                Custom http header
        -X value
                Request command to use (GET, POST)
        -clients int
                Number of clients (default 20)
        -command value
                Request command to use (GET, POST)
        -connect-timeout duration
                Maximum time allowed for connection (default 1s)
        -d value
                Post data; filenames are prefixed with @
        -data value
                Post data; filenames are prefixed with @
        -gradient float
                Accepted gradient of expected linear function (default 1.1)
        -header value
                Custom http header
        -iterations int
                Number of sucessive requests for every client (default 5)
        -no-color
                No color output

Every option can be given with a two dash prefix too.

## Example

    chail -clients 1 -iterations 1 -X POST -H "Content-Type: application/json" -H "Authorization: Bearer 243545" -d '{"info": "Updated"}'  http://localhost:8000/product/123

Send the following request:

        POST /product/123 HTTP/1.1
        Header["Authorization"] = ["Bearer 243545"]
        Header["Content-Type"] = ["application/json"]
        Header["Accept-Encoding"] = ["gzip"]
        Header["User-Agent"] = ["Go-http-client/1.1"]
        Header["Content-Length"] = ["19"]

## Future plans

* Add verbose option
* Support multi-part-request