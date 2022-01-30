# NodeJS: Express Authentication Middleware

Your company will release a task manager app soon. The team has already created an Express app with multiple paths for creating and managing tasks. As a Nodes developer in your company, you need to write an authentication middleware based on API keys to protect some routes and make it available only to users who provide valid API keys.

__The middleware must implement the following functionalities:__

- Complete the ``key-store.js`` module. The module's default export is an Express route handler function that:
  - Generate a new unique API key
  - Add it to the ``valid-keys.txt`` file
  - It responds with status 201 and the body ``{ "apiKey": API_KEY }`` is the newly generated API key.
- File keys must be stored per line. Each key must be unique and the line terminator/separator/delimiter for each key must be the Nodes end-of-line marker os.EOL
- Complete the module middlewares The default export of the module is an ExpressJS middleware function. This function should parse the ``api-key`` header and check if it is a valid key or not.
  - If it is a valid key, call the following function to pass control to the next function in the middleware stack
  - If the key is not valid or the header is not present, the server should respond with the 401 Status Code and does not pass control to the next function