# API Key Guard

A simple header-based API key authentication system built with NestJS. Built as a mini-project to learn NestJS Guards, ConfigModule, and global providers.

## How It Works

- Every incoming request is checked for an `x-api-key` header.
- If the header is missing or doesn't match the value in `.env`, the request is rejected with `401 Unauthorized`.
- If it matches, the request is forwarded to the controller.

## Setup

```bash
pnpm install
```

Create a `.env` file in the project root:
API_KEY=your-secret-key



## Running

```bash
pnpm run start:dev
```

The server runs on `http://localhost:3000`.

## Testing

Send a request to `GET /` with the header:

x-api-key: your-secret-key




- Missing or wrong key → `401 Unauthorized`
- Correct key → `200 OK`

## Tech Stack

- NestJS
- `@nestjs/config` (for reading `.env`)
- Global Guard (`APP_GUARD`)

## What I Learned

- Writing a custom Guard using the `CanActivate` interface
- Accessing the HTTP request via `ExecutionContext`
- Constructor-based dependency injection (`ConfigService`)
- Registering a global Guard using the `APP_GUARD` token