## Demo

```
git clone git@github.com:wacai/json-template-renderer.git
cd json-template-renderer
mvn clean package
java -Dsuffix.mapping=suffix.mapping -jar target/jtr-*.jar src/test/resources/webapp src/test/resources/models
```

1. Open <http://localhost:8080>
1. Click [home.jsp](http://localhost:8080/home.jsp)

## Template Supported List

* [x] [Java Server Pages][jsp] ([JSP Standard Tag Library][jstl])
* [x] [Velocity][vm]
* [ ] [FreeMarker][ftl]

[jsp]:http://www.oracle.com/technetwork/java/jsp-138432.html
[jstl]:http://www.oracle.com/technetwork/java/index-jsp-135995.html
[vm]:http://velocity.apache.org/
[ftl]:http://freemarker.org/

## Change Suffix Mapping

Edit file `suffix.mapping` like:

```
.action .jsp
```

> mapping `xxx.action` to `xxx.jsp`

Then, restart it.

## Choose other model

The name of model file would be some of template as default, like `home.jsp` with `home.json`.

Sometimes one template may rendered by multiple model files.
Please use query param to choose which model file should be rendered with template, for example:

<http://localhost:8080/home.jsp?m=other>

## More help

```
java -jar target/jtr-*.jar help
```

## Development Tips

### Run & Debug

```
mvn clean compile exec:exec
```

Use your favourite IDE setup remote debug to 5005