# Crunchyroll landing page clone

The app was written on Vue + Vite

<img width="1440" alt="Screenshot 2025-01-17 at 20 59 10" src="https://github.com/user-attachments/assets/924bca5e-44da-4472-a136-319251b6628b" />

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```

## Run development Dockerfile

### Build the development image

```sh
docker build -f Dockerfile.dev -t hifichevymane/crunchyroll-clone-dev .
```

### Run the development container

```sh
docker run -p 5173:5173 --name crunchyroll-clone-dev hifichevymane/cruncyroll-clone-dev
```

## Run production Dockerfile

### Build the production image

```sh
docker build -f Dockerfile.prod -t hifichevymane/crunchyroll-clone-prod .
```

### Run the production container

```sh
docker run -p 8080:80 --name crunchyroll-clone-prod hifichevymane/cruncyroll-clone-prod
```
