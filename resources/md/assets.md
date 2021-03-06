The assets for the application are located under the `resources` folder. Assets include any non-source files that you may
wish to include in the application. These may be database migration files, SQL query files, and so on. The `resources/public`
folder is reserved for assets that will be served directly by the HTTP server. This is where you would place assets such as images and CSS.

Luminus has integrated support for [WebJars](http://www.webjars.org/) and defaults to including external assets, such as
Twitter Bootstrap, via this method. Twitter Bootstrap is included as a dependency in the project `[org.webjars/bootstrap "4.0.0-alpha.2"]`.
Its contents are made available using the [ring-webjars](https://github.com/weavejester/ring-webjars) middleware.

Once the library is included, its assets become available on the classpath and can be accessed in the HTML templates
using the `/assets` prefix. as seen below:

```xml
{% style "/assets/bootstrap/css/bootstrap.min.css" %}
{% style "/assets/font-awesome/css/font-awesome.min.css" %}
```

The `ring-webjars` library strips out the version number from the included assets. The asset
referenced as `/assets/bootstrap/css/bootstrap.min.css` is found on the classpath as
`/webjars/bootstrap/4.0.0-alpha.2/css/bootstrap.min.css`.
