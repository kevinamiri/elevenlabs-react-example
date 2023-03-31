# Elevenlabs AudioStream React Example

The `AudioStream` component is a simple and reusable React component that allows users to convert text to speech using the ElevenLabs API.


## Component Props

The `AudioStream` component accepts the following props:

| Prop Name | Type | Required | Description |
| --- | --- | --- | --- |
| **`voiceId`** | **`string`** | Yes | The Voice ID to be used for text-to-speech conversion. |
| **`text`** | **`string`** | Yes | The text to be converted into speech. |
| **`apiKey`** | **`string`** | Yes | Your ElevenLabs API key. |
| **`voiceSettings`** | **`VoiceSettings`** | Yes | An object containing voice settings such as **`stability`** and **`similarity_boost`**. |

`VoiceSettings` interface:

```javascript
interface VoiceSettings {
  stability: number;
  similarity_boost: number;
}
```

## Usage

To use the `AudioStream` component in your React application, follow these steps:

1. Install the necessary dependencies:

```javascript
npm install axios react react-dom @types/react @types/react-dom
```

2. Import the `AudioStream` component:

```javascript
import AudioStream from './AudioStream';
```

3. Add the `AudioStream` component to your JSX or TSX:

```javascript
tsxCopy code
<AudioStream voiceId={voiceId} text={text} apiKey={apiKey} voiceSettings={voiceSettings} />
```

Replace `voiceId`, `text`, `apiKey`, and `voiceSettings` with the appropriate values based on your ElevenLabs API settings.



Example:

```javascript
// index.tsx
import React from 'react';
import ReactDOM from 'react-dom';
import AudioStream from './AudioStream';

const voiceId = '21m00Tcm4TlvDq8ikWAM';
const text = 'Hello, this is a sample text to stream as speech.';
const apiKey = 'your-api-key-here';
const voiceSettings = {
  stability: 0,
  similarity_boost: 0,
};

ReactDOM.render(
  <React.StrictMode>
    <AudioStream voiceId={voiceId} text={text} apiKey={apiKey} voiceSettings={voiceSettings} />
  </React.StrictMode>,
  document.getElementById('root')
);

```

This will render the `AudioStream` component with a "Start Streaming" button. When the button is clicked, the text-to-speech conversion will begin, and the generated audio will play.
