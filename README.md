# fasthtml-sse

This example implements a chatbot. Most parts are copied from the [fasthtml chatbot example](https://github.com/AnswerDotAI/fasthtml-example/blob/main/02_chatbot/README.md).  

However instead of using websockets, this example uses Server-Sent Events (SSE) to send messages from the server to the client.
On message submission, the server responds with the user message and an empty assitant message. This assistant message element initializes the SSE connection and receives the streaming messages from the server. After the final message is sent, a `close` event from the server closes the connection.
