# Getting Started with the Unsplash API

The [Unsplash API](https://unsplash.com/developers) provides developers with free access to millions of high-quality images. With it, you can search, fetch, and integrate photos directly into your applications.

This guide walks you through the setup process and explains the different authentication options available.

---

## 1. Create a Developer Account

To begin, create a developer [account on Unsplash](https://unsplash.com/oauth/applications).

Once your account is set up:

1. Navigate to the [**Your Apps**](https://unsplash.com/oauth/applications) page.
2. Click **New Application**.
3. Fill out the required details and accept the terms.

<img src="/img/acceptTerms.png" alt="terms and condition form" />

When created, your app will start in **demo mode**:

* Limited to **50 requests per hour**.
* Perfect for demos, testing, or educational projects.

<img src="/img/demoImage.png" alt="terms and condition form" />

:::tip NOTE
👉 To increase your rate limit, you’ll need to apply for **Production Access** by following the *Apply for Production* instructions in your app settings. If approved, your app will receive higher request limits.
:::
---

## 2. Base URL

All requests to the Unsplash API use the following **base URL**:

```
https://api.unsplash.com/
```

Responses are returned in **JSON** format.

---

## 3. Retrieve Your Access Key

Each registered application is assigned two keys:

* **Access Key** → Used in requests (safe to expose in public apps).
* **Secret Key** → Keep private; used for OAuth and server-side requests.

To get your **Access Key**:

1. Go to the app you created under *Your Apps*.
2. Scroll down to view your **Access Key**.


<img src="/img/accessKey.jpeg" alt="access key animation" />
---

## 4. Authentication

- ### Public Authentication

Most actions (searching, fetching, downloading photos) do **not** require user-specific authentication.

There are two ways to authenticate your requests:

#### Option 1: Authorization Header

```bash
Authorization: Client-ID YOUR_ACCESS_KEY
```

#### Option 2: Query Parameter

```bash
https://api.unsplash.com/photos/?client_id=YOUR_ACCESS_KEY
```
:::tip TIP
 Most developers use the query parameter method. It doesn’t require user login and is cacheable, making it faster in many cases.
:::

If you attempt non-public actions (e.g., liking a photo, fetching private collections) with only an access key, you’ll receive a **401 Unauthorized** response.

---

- ### User Authentication

For apps that need to interact with Unsplash **on behalf of a user**, you’ll need to use the **OAuth workflow** to generate **Bearer tokens**.

This allows you to:

* Check if a user has liked a photo.
* Fetch private collections.
* Perform actions (like, follow, etc.) as the user.

📖 See the [User Authentication Guide](https://unsplash.com/documentation#authorization) for step-by-step instructions.

---

- ### Dynamic Client Registration

For decentralized platforms (e.g., **WordPress**, **Ghost**), where a single shared API key isn’t possible, Unsplash supports **Dynamic Client Registration**.

This grants **unique API keys per user**, with a simplified sign-up flow.

Learn more in the [Dynamic Client Registration documentation](https://unsplash.com/documentation#registering-an-application).

---

## Example Request in Postman

To test the Unsplash API in Postman:

1. Open Postman and create a new request.
2. Set the method to **GET** and paste this URL:

```bash
https://api.unsplash.com/photos/random?query=nature
```

markdown
Copy
Edit

3. Go to the **Headers** tab and add the following:
- **Key:** `Authorization`  
- **Value:** `Client-ID YOUR_ACCESS_KEY`

4. Click **Send** to get the response.

<img src="/img/postmanImage.jpeg" alt="access key animation" />

All you have to do is swap the endpoints according to your preference. You can check out some endpoint and their responses in this documentation.