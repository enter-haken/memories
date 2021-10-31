```
id: 7e71a481-4982-4ca6-9262-d1d7815da23e
title: React with Phoenix socket
links:
  - 1fbb1e40-3b6d-11ea-a667-77559ebd764b
  - 51d1b9b4-3b6f-11ea-abc5-2b9a48d028a7
```

# phoenix-js-react-hooks

Wrap the top of your app with a <SocketProvider> so child components will have
access to the socket.


```elixir
import { SocketProvider } from '@ericlathrop/phoenix-js-react-hooks';

function App() {
  const socketUrl = "wss://localhost:4000/socket";
  const socketOptions = { params: { 'user_id': userId }};

  return (
    <SocketProvider url={socketUrl} options={socketOptions}>
      <Main />
    </SocketProvider>
  );
}
```

The useChannel hook lets you subscribe to a channel, and the useEventHandler
hook lets you handle incoming messages:

```javascript
import React, { useContext, useEffect, useRef, useState } from 'react';
import { sendMessage, useChannel, useEventHandler } from '@ericlathrop/phoenix-js-react-hooks';

export function Main() {
  const [messages, setMessages] = useState([]);

  const room = 'cute kitties';
  const { channel: chatChannel } = useChannel('chat:' + room, undefined, (channel, { messages: initialMessages}) => {
    setMessages(initialMessages);
  });

  useEventHandler(chatChannel, 'new_message', message => {
    setMessages(messages.slice(0).concat([message]));
  });

  return (
    <div className="chat-messages" >
      {messages.map(({ id, message }) => <ChatMessage key={id} message={message} />)}
    </div>
  );
}
```

...

[phoenix-js-react-hooks][1]

[1]: https://gitlab.com/ericlathrop/phoenix-js-react-hooks 
