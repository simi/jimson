# Jimson
### JSON-RPC 2.0 Client and Server for Ruby

## Client: Quick Start
    client = Jimson::Client.new("http://www.example.com:8999") # the URL for the JSON-RPC 2.0 server to connect to
    result = client.sum(1,2) # call the 'sum' method on the RPC server and save the result '3'

## Server: Quick Start
    class MyHandler
      extend Jimson::Handler 

      def sum(a,b)
        a + b
      end
    end

    server = Jimson::Server.new(MyHandler.new)
    server.start # serve with webrick on http://0.0.0.0:8999/
