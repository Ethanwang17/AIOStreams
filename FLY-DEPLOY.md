# Deploying AIOStreams to Fly.io

## Prerequisites

1. Install the Fly.io CLI:
   ```bash
   # macOS
   brew install flyctl
   # or
   curl -L https://fly.io/install.sh | sh
   ```

2. Login to Fly.io:
   ```bash
   fly auth login
   ```

## Deployment Steps

1. Launch your app (first-time only):
   ```bash
   fly launch --dockerfile Dockerfile --name aiostreams
   ```
   - This will use your existing Dockerfile
   - You can choose to deploy now or later
   - You may need to add a payment method even for the free tier

2. For subsequent deployments:
   ```bash
   fly deploy
   ```

3. Open your deployed app:
   ```bash
   fly open
   ```

## Configuration

- The app is configured to use the settings in `fly.toml`
- The app will run on port 3000 internally and be exposed via HTTPS
- Auto-scaling is enabled with scale-to-zero functionality

## Monitoring

- View app status:
  ```bash
  fly status
  ```

- View logs:
  ```bash
  fly logs
  ```

## Scaling

- Scale your app:
  ```bash
  fly scale count 2  # Set to desired number of instances
  ```

## Troubleshooting

- SSH into your VM:
  ```bash
  fly ssh console
  ```

- Check resource usage:
  ```bash
  fly status
  ```

- Restart your app:
  ```bash
  fly apps restart
  ``` 