# Spotify Canvas Downloader

Tool to get Canvas cover videos from Spotify tracks.

## ✨ [Try it out](https://canvastify.delitefully.com)

### Start Script

step 1: pip install requirements.txt
step 2: uvicorn app:app --host localhost --port 3000

### Building

- Clone the repository
  ```sh
  git clone https://github.com/Delitefully/spotify-canvas-downloader
  ```
- Configure the env variables
  ```sh
  mv env.example .env
  ```
- Build the image using Docker Compose
  ```sh
  docker-compose up
  ```

### Development

Recompile protocol buffer proto (useful when upgrading protobuff):

```
protoc ./protos/canvas.proto  --python_out=./src/
```

Requires the [Protocol Buffers package](https://developers.google.com/protocol-buffers/docs/downloads).

### API

```http
GET /api/canvas/:trackId
```

Returns

```json
{
    "success": boolean
    "canvas_url": string, if success is 'true'
    "message": string, error message if success is 'false'
}
```
