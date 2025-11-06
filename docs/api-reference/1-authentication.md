---
title: Authentication
slug: authentication
sidebar_position: 2
---

All requests made to the Cogfy Messenger API must be authenticated. This is done by providing an API key in the headers of each request:

```
Api-Key: <COGFY_MESSENGER_API_KEY>
```

:::danger
Make sure to keep your API key secure.
Do not expose the API key in public repositories or client-side code.
:::

## Managing API Keys

API Keys can be managed in the Cogfy app at `https://messenger.cogfy.com/<YOUR_WORKSPACE>/settings/api-keys`.

:::info
Each API key is associated with a single workspace.
:::

## Examples


### Node.js

An example of making a call to the Cogfy Messenger API using the `fetch` function:

```typescript
const sendMessage = await fetch(
  'https://messenger-public-api.cogfy.com/messages/text',
  {
    headers: {
      'Api-Key': process.env.COGFY_MESSENGER_API_KEY
    },
    body: {
      'from': 'string',
      'to': 'string',
      'text': {
        'body': 'string'
      }
    }
  }
)
const result = await sendMessage.json()
```
