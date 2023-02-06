# Environment

| Environment | Base URL                              |
|-------------|---------------------------------------|
| Sandbox     | https://open-api.sandbox.paper.id/api |
| Production  | https://apis.paper.id/api             |


For the front end side (dashboard) you can access via these URL

| Environment | Dashboard  URL                        |
|-------------|---------------------------------------|
| Sandbox     | https://sandbox.paper.id/webappv1/    |
| Production  | https://paper.id/webappv1/            |

Response Code
Description Of Usual Server Responses:
1. <span style="color: blue">200</span> OK - the request was successful (some API calls may return 201 instead).
2. <span style="color: blue">201</span> Created- the request was successful and a resource was created.
3. <span style="color: blue">204</span> No Content- the request was successful but there is no representation to return (i.e. the response is empty).
4. <span style="color: red">400</span> Bad Request- the request could not be understood or was missing required parameters.
5. <span style="color: red">401</span> Unauthorized- authentication failed or user doesn't have permissions for requested operation.
6. <span style="color: red">403</span> Forbidden - access denied.
7. <span style="color: red">404</span> Not Found- resource was not found.
8. <span style="color: red">405</span> Method Not Allowed- requested method is not supported for resource.
9. <span style="color: gray">500</span> Internal Server Error- It means that the server encountered an unexpected condition that prevented it from fulfilling the request.