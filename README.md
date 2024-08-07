# fasthtml-sse

This example implements a chatbot. Most parts are copied from the [fasthtml chatbot example](https://github.com/AnswerDotAI/fasthtml-example/blob/main/02_chatbot/README.md).  

However instead of using websockets, this example uses [**server-sent events (SSE)**](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events/Using_server-sent_events) to send messages from the server to the client.

On message submission, the server responds with 2 message `Div`s - the *user message* and an *empty assistant message*.  
This assistant message element initializes the SSE connection and receives the streaming messages from the server. After the final message is sent, a `close` event from the server closes the connection.

This process repeats on every message submission. As the connection to the server is terminated after every message, the server only needs to be running a couple of (milli-)seconds, enabling deployments using serverless functions like AWS Lambda or Azure Functions.
