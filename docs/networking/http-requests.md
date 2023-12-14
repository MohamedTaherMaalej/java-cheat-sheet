# HTTP Requests in Java

Making HTTP requests in Java is a common task for interacting with web services and APIs. Java provides several libraries, such as `HttpURLConnection` and third-party libraries like Apache HttpClient, for handling HTTP requests. Here, we'll cover the fundamentals of making HTTP requests in Java.

## Using `HttpURLConnection` (Java Standard Library)

The `HttpURLConnection` class is part of the Java Standard Library and provides a simple way to send HTTP requests and receive responses.

### Making a GET Request

```java
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.BufferedReader;
import java.io.InputStreamReader;

public class HttpGetExample {
    public static void main(String[] args) {
        try {
            URL url = new URL("https://api.example.com/data");
            HttpURLConnection connection = (HttpURLConnection) url.openConnection();

            // Set the request method
            connection.setRequestMethod("GET");

            // Read the response
            try (BufferedReader reader = new BufferedReader(new InputStreamReader(connection.getInputStream()))) {
                String line;
                while ((line = reader.readLine()) != null) {
                    System.out.println(line);
                }
            }

            // Close the connection
            connection.disconnect();
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

### Making a POST Request

```java
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.OutputStream;
import java.io.OutputStreamWriter;

public class HttpPostExample {
    public static void main(String[] args) {
        try {
            URL url = new URL("https://api.example.com/data");
            HttpURLConnection connection = (HttpURLConnection) url.openConnection();

            // Set the request method
            connection.setRequestMethod("POST");
            connection.setDoOutput(true);

            // Write the request body
            try (OutputStream outputStream = connection.getOutputStream();
                 OutputStreamWriter writer = new OutputStreamWriter(outputStream)) {
                writer.write("key1=value1&key2=value2");
            }

            // Read the response
            try (BufferedReader reader = new BufferedReader(new InputStreamReader(connection.getInputStream()))) {
                String line;
                while ((line = reader.readLine()) != null) {
                    System.out.println(line);
                }
            }

            // Close the connection
            connection.disconnect();
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

## Using Apache HttpClient

Apache HttpClient is a third-party library that provides a more feature-rich and flexible way to work with HTTP requests.

### Adding Apache HttpClient Dependency

To use Apache HttpClient, add the following Maven dependency:

```xml
<dependency>
    <groupId>org.apache.httpcomponents</groupId>
    <artifactId>httpclient</artifactId>
    <version>4.5.13</version> <!-- Replace with the latest version -->
</dependency>
```

### Making a GET Request

```java
import org.apache.http.HttpResponse;
import org.apache.http.client.HttpClient;
import org.apache.http.client.methods.HttpGet;
import org.apache.http.impl.client.HttpClients;
import java.io.BufferedReader;
import java.io.InputStreamReader;

public class ApacheHttpGetExample {
    public static void main(String[] args) {
        try {
            HttpClient httpClient = HttpClients.createDefault();
            HttpGet httpGet = new HttpGet("https://api.example.com/data");

            HttpResponse response = httpClient.execute(httpGet);

            // Read the response
            try (BufferedReader reader = new BufferedReader(new InputStreamReader(response.getEntity().getContent()))) {
                String line;
                while ((line = reader.readLine()) != null) {
                    System.out.println(line);
                }
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

### Making a POST Request

```java
import org.apache.http.HttpResponse;
import org.apache.http.client.HttpClient;
import org.apache.http.client.methods.HttpPost;
import org.apache.http.entity.StringEntity;
import org.apache.http.impl.client.HttpClients;
import java.io.BufferedReader;
import java.io.InputStreamReader;

public class ApacheHttpPostExample {
    public static void main(String[] args) {
        try {
            HttpClient httpClient = HttpClients.createDefault();
            HttpPost httpPost = new HttpPost("https://api.example.com/data");

            // Set the request body
            httpPost.setEntity(new StringEntity("key1=value1&key2=value2"));

            HttpResponse response = httpClient.execute(httpPost);

            // Read the response
            try (BufferedReader reader = new BufferedReader(new InputStreamReader(response.getEntity().getContent()))) {
                String line;
                while ((line = reader.readLine()) != null) {
                    System.out.println(line);
                }
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

## Summary

- Java provides the `HttpURLConnection` class in the standard library for basic HTTP requests.
- Apache HttpClient is a third-party library that offers a more feature-rich alternative.
- Use `GET` requests to retrieve data and `POST` requests to send data to a server.
- Handle exceptions appropriately when making HTTP requests.

For more details on HTTP requests in Java, refer to the [official Java documentation](https://docs.oracle.com/javase/tutorial/networking/urls/index.html) and [Apache HttpClient documentation](https://hc.apache.org/httpcomponents-client-4.5.x/tutorial/html/index.html).
