
// In your ARIA chat widget - works for ALL platforms
const response = await fetch('/api/chat', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({
    model: 'claude-sonnet-4-6',
    max_tokens: 1000,
    system: 'You are ARIA, SecureID security advisor...',
    messages: conversationHistory
  })
});
const data = await response.json();
render.yaml
public_html/
├── index.html              ← React build output
├── static/                 ← React assets
└── .htaccess               ← URL rewriting

secureid-api/               ← outside public_html!
├── server.js
├── package.json
└── .env

/var/www/secureid/
├── client/                 ← React build files
│   └── build/
├── server/
│   ├── server.js           ← Express proxy
│   ├── package.json
│   └── .env                ← API key stored here
└── ecosystem.config.js     ← PM2 process manager



