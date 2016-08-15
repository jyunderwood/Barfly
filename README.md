# Barfly

Verify barcodes as a service.

A [Spring Boot](http://projects.spring.io/spring-boot/) application that uses the [ZXing](https://github.com/zxing/zxing) library for decoding barcodes from images.

## Up and running

Have [gradle](https://gradle.org) installed or use the gradle wrapper.

```
./gradlew idea   # Prep for intellij development
./gradlew build  # Fetch deps and build project
./gradlew run    # Boot spring
```

## Using

Once running, post a multipart request to the upload path:

```curl
curl -X POST \
  -F "file=@test_barcode.png" \
  http://localhost:8080/upload
```

or visit [http://localhost:8080](http://localhost:8080) and upload an image of a barcode via the web form.

## Deploying

It's pretty easy to deploy to [Heroku](https://heroku.com):

- Create a Heroku application
- Add the heroku git repo as a remote
- `git push heroku master`

Alternatively, you can build a war file with: `./gradlew war`.
