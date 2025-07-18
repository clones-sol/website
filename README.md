# Clones Website

This is the website for Clones project.


## Developing

### Option 1: Development with Docker (Recommended)

The easiest way to run the project is using Docker Compose:

```bash
# Start the development server with Docker
docker compose up

# The app will be available at http://localhost:5173
```

This will:
- Build the development Docker image
- Install all dependencies
- Start the Vite development server
- Enable hot reloading for development

### Option 2: Local Development

If you prefer to run locally, first install dependencies:

```bash
npm install
```

Then start the development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

### Local Production Build

To create a production version of your app:

```bash
npm run build
```

You can preview the production build with `npm run preview`.

### Docker Production Build

To build the production Docker image:

```bash
docker build -t clones-website .
```

## Deployment

### Fly.io Deployment

This project is configured for deployment on Fly.io with two environments:

#### Automatic Deployment

- **Production**: Automatically deploys to `clones-website-prod` when pushing to the `main` branch
- **Test**: Automatically deploys to `clones-website-test` when pushing to the `test` branch

#### Manual Deployment

For manual deployment, ensure you have the Fly CLI installed and configured:

```bash
# Deploy to test environment
flyctl deploy -c fly.test.toml

# Deploy to production environment  
flyctl deploy -c fly.prod.toml
```

#### Environment Configuration

- **Production**: Uses `https://clones-backend-test.fly.dev` as API URL
- **Test**: Uses `https://clones-backend-test.fly.dev` as API URL
- **Development**: Uses `http://localhost:8001` as API URL

### Requirements

- Node.js LTS
- Docker and Docker Compose (for Docker development)
- Fly CLI (for manual deployment)

> To deploy your app to other platforms, you may need to install an [adapter](https://svelte.dev/docs/kit/adapters) for your target environment.
