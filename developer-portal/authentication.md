# Authentication

Before using the API, reach out to Paper.id team to get your client and account created. The PAPER.ID API's are authenticated using Basic Auth. Basic auth requires the following:

| Key            | Value                |
|----------------|----------------------|
| client_id      | [YOUR_CLIENT_ID]     |
| client_secret  | [YOUR_CLIENT_SECRET] |

Basic auth expects an Authorization header for each request in the basic base 64 token format. 
Your client_id and client secrets carry many privileges, so be sure to keep them secure! Do not share your secret API keys in publicly accessible areas such as GitHub, 
client-side code, and so forth.

All API requests must be made over HTTPS. Calls made over plain HTTP will fail. API requests without authentication will also fail.