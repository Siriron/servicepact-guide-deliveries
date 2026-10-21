# Delivery

engagement:g-paid-cua89u
contractor:0xb1d236988a76b3e978de66b1c45278c6d17fa8ba

This delivery contains the three items listed in the statement of work: the login page, the API client module and the README.

## 1. Login page (login.html)

<form id="login" action="/session" method="post">
  <label for="email">Email</label>
  <input id="email" name="email" type="email" required>
  <label for="password">Password</label>
  <input id="password" name="password" type="password" required minlength="8">
  <button type="submit">Sign in</button>
</form>

## 2. API client module (api.js)

const BASE = "/api";

export async function request(path, options) {
  const init = options || {};
  const response = await fetch(BASE + path, {
    method: init.method || "GET",
    headers: { "Content-Type": "application/json" },
    body: init.body ? JSON.stringify(init.body) : undefined,
  });
  if (!response.ok) {
    throw new Error("Request to " + path + " failed with status " + response.status);
  }
  return response.json();
}

## 3. README (README.md)

Install: run npm install.
Run: run npm start and open http://localhost:3000/login.html.
Test: run npm test.
Sign in with the account created by npm run seed.
The API client is imported with: import { request } from "./api.js".
