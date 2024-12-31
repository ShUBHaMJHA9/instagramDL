# Instagram Videos Downloader

A simple website and API for downloading Instagram videos, built with Next.js.

## Description

This project allows users to download Instagram videos easily by pasting the URL of any public Instagram post. The tool supports video downloads in MP4 format and includes an API for integrating this functionality into your own applications.

**Note:** Instagram Stories are not supported.

You can preview the live website here: [Instagram Video Downloader](https://instagramdl-6orw.onrender.com).

## Website Features

- **User-friendly interface:** Interactive feedback and error messages.
- **Responsive design:** Optimized for both desktop and mobile devices.

### Desktop Preview

![Desktop preview](https://github.com/riad-azz/readme-storage/blob/main/instagram-videos-downloader/desktop-preview.gif?raw=true)

### Mobile Preview

![Mobile preview](https://github.com/riad-azz/readme-storage/blob/main/instagram-videos-downloader/mobile-preview.gif?raw=true)

---

## How to Run the Project

### Using Docker

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-github-username>/<your-repo-name>.git
   ```

2. Build the Docker image:
   ```bash
   docker build -t instagram-video-downloader .
   ```

3. Run the Docker container:
   ```bash
   docker run -p 3000:3000 instagram-video-downloader
   ```

### Using Node.js

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-github-username>/<your-repo-name>.git
   ```

2. Navigate to the project directory:
   ```bash
   cd <your-repo-name>
   ```

3. Install dependencies:
   ```bash
   npm install
   ```

4. Start the server:
   ```bash
   # For development
   npm run dev

   # Build the project
   npm run build

   # Start the production server
   npm run start
   ```

---

## API Documentation

### Endpoint: `/api/video?postUrl={POST_URL}`

#### Parameters:

- `postUrl` (required): The link to an Instagram Post or Reel.

#### Example GET Request

```bash
curl -i "http://localhost:3000/api/video?postUrl=https://www.instagram.com/p/CGh4a0iASGS"
```

#### Example API Response

```json
{
  "status": "success",
  "data": {
    "filename": "ig-downloader-1712666263.mp4",
    "width": "640",
    "height": "640",
    "videoUrl": "https://scontent.cdninstagram.com/o1/v/t16/f1/m84/E84E5DFC48EA8...etc"
  }
}
```

---

## Rate Limiting with Upstash

Rate limiting is implemented to ensure optimal performance and restrict excessive API usage.

### Enabling Rate Limiting:

1. Sign up at [upstash.com](https://upstash.com/).
2. Create a new Redis database.
3. Copy the REST API credentials from the database settings.
4. Create a `.env.local` file in the root directory and add the following:

   ```env
   USE_UPSTASH="true"
   UPSTASH_REDIS_REST_URL="YOUR-UPSTASH-URL"
   UPSTASH_REDIS_REST_TOKEN="YOUR-UPSTASH-TOKEN"
   ```

5. Modify any rate-limit configurations in `src/features/ratelimit/constants.ts`.

---

## License

This project is licensed under the [MIT License](LICENSE.md).

---

For more details or contributions, check the repository: [GitHub Repository](https://github.com/<your-github-username>/<your-repo-name>).

