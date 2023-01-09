# Serverless Functions

## Reading

* [What is Serverless Computing?](https://www.ibm.com/cloud/learn/serverless)

## Resources

* [venv - Creation of Virtual Environments](https://docs.python.org/3/library/venv.html)
* [Vercel - Get Started](https://vercel.com/docs/get-started)
* [http.server](https://pymotw.com/3/http.server/index.html)
* [Requests](https://requests.readthedocs.io/en/latest/)
* [Python & APIs](https://realpython.com/python-api/)

## Reference

* [Serverless Functions](https://vercel.com/docs/concepts/functions/serverless-functions)
* [Effective Python Environment](https://realpython.com/effective-python-environment/)


## Notes

### What is Serverless?

Serverless is a type of computing that allows you to run code or applications without having to worry about managing the underlying servers. Instead of provisioning and maintaining servers to run your code, you can simply write and deploy your application to a cloud provider that handles all of the infrastructure for you. The term "serverless" does not mean "no servers", but rather describes the experience of the developer; the server is invisible to them.

With a serverless model, you only pay for the resources you consume, such as the number of times your code is executed or the amount of computing time it consumes. This can be more cost-effective than running your own servers, since you only pay for what you use and don't have to worry about the overhead of maintaining the infrastructure. In other words, **developers never pay to idle capacity**. The cloud provider spins the server up when code executes and "*scales to zero*" when done executing. This model is known as *Functions-as-a-Service* (FaaS).

### Create a Virtual Environment

`venv` is a module in Python that allows you to create virtual environments. A virtual environment is a separate environment on your computer that allows you to install packages and Python modules in isolation from the global Python environment. This can be useful for a variety of reasons, such as:

* Installing packages that have conflicting dependencies or requirements with other packages that you use.
* Testing packages or code in an isolated environment before deploying them to a production environment.
* Working on multiple projects that require different versions of the same package.
* To create a virtual environment using `venv`, you can use the following steps:

  1. Open a terminal and navigate to the directory where you want to create your virtual environment.
  2. Run the following command to create a virtual environment: `python3 -m venv myenv`, where `myenv` is the name of your virtual environment.
     * **NOTE**
       * Replace `python3` with specific version you need are running for the project
       * If already in the program when setting up the venv, you can just use `python3 -m venv .venv` to add a `.venv` file to the root of the directory
  3. Activate the virtual environment by running the following command: `source myenv/bin/activate` (on Linux or macOS) or `myenv\Scripts\activate` (on Windows).
  4. Your virtual environment is now active, and any packages that you install using pip will be installed in the virtual environment instead of the global Python environment.
  5. When you are finished working in the virtual environment, you can deactivate it by running the deactivate command.

You can also use the `venv` module to create virtual environments with different versions of Python. For example, you can use the `--python` flag to specify the path to a specific version of Python, like this: `python3 -m venv myenv --python=python3.9`. This will create a virtual environment that uses Python 3.9 instead of the default version of Python that is installed on your system.

### How does a venv work?

When you create a virtual environment using the `venv` module, it creates a new directory on your computer that contains a copy of the Python interpreter, as well as a copy of the `pip` package manager. This allows you to have a separate Python environment that is isolated from the global Python environment on your system.

When you activate a virtual environment, the `activate` script modifies your shell's `PATH` environment variable to include the directories for the virtual environment's Python interpreter and `pip` executables. This ensures that when you run `python` or `pip` from the command line, the correct executables from the virtual environment are used instead of the ones from the global environment.

When you install a package using `pip` while a virtual environment is active, the package is installed in the virtual environment's copy of the Python package directory, rather than the global package directory. This allows you to have multiple versions of the same package installed on your system, with each version installed in a separate virtual environment.

When you deactivate a virtual environment, the `deactivate` script modifies your shell's `PATH` environment variable to remove the directories for the virtual environment's executables. This ensures that you are using the global Python environment again until you activate another virtual environment.

### Python and APIs

#### http.server — Base Classes for Implementing Web Servers

http.server uses classes from [socketserver](https://pymotw.com/3/socketserver/index.html#module-socketserver) to create base classes for making HTTP servers.

* **Create**

  ```py
  from http.server import BaseHTTPRequestHandler, HTTPServer
  import json

  class CreateHandler(BaseHTTPRequestHandler):
      def do_POST(self):
          # Read the request body and parse it as JSON
          data = self.rfile.read(int(self.headers["Content-Length"]))
          data = json.loads(data)

          # Create a new resource using the data from the request body
          new_resource = create_resource(data)

          # Set the response status code to 201 (Created)
          self.send_response(201)

          # Set the response headers
          self.send_header("Content-Type", "application/json")
          self.end_headers()

          # Write the response body as a JSON-encoded representation of the new resource
          self.wfile.write(json.dumps(new_resource).encode())

  def create_server():
      server = HTTPServer(("", 8000), CreateHandler)
      server.serve_forever()

  create_server()
  ```

* **Read**

  ```py
  from http.server import BaseHTTPRequestHandler, HTTPServer
  import json

  class ReadHandler(BaseHTTPRequestHandler):
      def do_GET(self):
          # Parse the resource ID from the request URL
          resource_id = self.path.split("/")[-1]

          # Retrieve the resource from the database
          resource = get_resource(resource_id)

          # Set the response status code to 200 (OK)
          self.send_response(200)

          # Set the response headers
          self.send_header("Content-Type", "application/json")
          self.end_headers()

          # Write the response body as a JSON-encoded representation of the resource
          self.wfile.write(json.dumps(resource).encode())

  def create_server():
      server = HTTPServer(("", 8000), ReadHandler)
      server.serve_forever()

  create_server()
  ```

* **Update**

  ```py
  from http.server import BaseHTTPRequestHandler, HTTPServer
  import json

  class RequestHandler(BaseHTTPRequestHandler):
      def do_PUT(self):
          # Parse the resource ID from the request URL
          resource_id = int(self.path.split('/')[-1])

          # Read the request body and parse it as JSON
          content_length = int(self.headers['Content-Length'])
          body = self.rfile.read(content_length).decode()
          data = json.loads(body)

          # Update the resource with the data from the request
          resource = update_resource(resource_id, data)

          # Set the response status code to 200 (OK)
          self.send_response(200)

          # Set the response header to indicate that the response contains JSON
          self.send_header('Content-Type', 'application/json')
          self.end_headers()

          # Write the JSON representation of the updated resource to the response body
          self.wfile.write(json.dumps(resource).encode())

  def update_resource(resource_id, data):
      # Update the resource with the data from the request
      resource = {'id': resource_id, 'name': data['name']}
      return resource

  server = HTTPServer(('localhost', 8000), RequestHandler)
  server.serve_forever()
  ```

* **Delete**

  ```py
  from http.server import BaseHTTPRequestHandler, HTTPServer

  class RequestHandler(BaseHTTPRequestHandler):
      def do_DELETE(self):
          # Parse the resource ID from the request URL
          resource_id = int(self.path.split('/')[-1])

          # Delete the resource
          delete_resource(resource_id)

          # Set the response status code to 204 (No Content)
          self.send_response(204)
          self.end_headers()

  def delete_resource(resource_id):
      # Delete the resource from storage
      pass

  server = HTTPServer(('localhost', 8000), RequestHandler)
  server.serve_forever()
  ```

### Request Library for API Calls

* Need to install: `python -m pip install requests`

* CRUD examples

  ```py
  import requests

  # Set the base URL for the API endpoint
  base_url = "https://api.example.com"

  # Set the endpoint path
  endpoint = "/users"

  # Set the headers for the request
  headers = {
      "Content-Type": "application/json",
      "Authorization": "Bearer abc123"
  }

  # Set the payload for the request
  payload = {
      "name": "John Smith",
      "email": "john@example.com"
  }

  # Send a POST request to create a new resource
  response = requests.post(base_url + endpoint, headers=headers, json=payload)

  # Print the response status code
  print(response.status_code)

  # Print the response body
  print(response.json())

  # Set the resource ID for the resource we just created
  resource_id = 123

  # Send a GET request to read the resource
  response = requests.get(base_url + endpoint + '/' + str(resource_id), headers=headers)

  # Print the response status code
  print(response.status_code)

  # Print the response body
  print(response.json())

  # Set the updated payload for the request
  payload = {
      "name": "John Doe",
      "email": "john@example.com"
  }

  # Send a PUT request to update the resource
  response = requests.put(base_url + endpoint + '/' + str(resource_id), headers=headers, json=payload)

  # Print the response status code
  print(response.status_code)

  # Print the response body
  print(response.json())

  # Send a DELETE request to delete the resource
  response = requests.delete(base_url + endpoint + '/' + str(resource_id), headers=headers)

  # Print the response status code
  print(response.status_code)
  ```

* Detailed `GET` request

  ```py
  import requests

  # Set the base URL for the API endpoint
  base_url = "https://api.example.com"

  # Set the endpoint path
  endpoint = "/users"

  # Set the API key
  api_key = "abc123"

  # Set the headers for the request
  headers = {
      "Content-Type": "application/json",
      "Authorization": "API-Key " + api_key
  }

  # Send a GET request to read a resource
  response = requests.get(base_url + endpoint + '/123', headers=headers)

  # Print the response status code
  print(response.status_code)

  # Print the response body
  print(response.json())
  ```
