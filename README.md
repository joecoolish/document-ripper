# document-ripper
Tika based document ripper.

Example HTTP calls:

## Detect Steam (Content-Type)

```
PUT /detect/stream HTTP/1.1
Host: 10.0.75.2:9998
Accept: text/plain
fileUrl: http://logicappengine:3000/file/datashare/big-buck-bunny_trailer(1).webm
cache-control: no-cache
```

## Get Recursive Metadata

```
PUT /rmeta HTTP/1.1
Host: 10.0.75.2:9998
Accept: application/json
fileUrl: http://logicappengine:3000/file/datashare/SampleVideo_1280x720_5mb.mp4
Content-Type: video/mpeg
cache-control: no-cache
```

> Note: `Content-Type` should be the output of Detect Stream


## Get Content (Text)

```
PUT /tika HTTP/1.1
Host: 10.0.75.2:9998
fileUrl: http://logicappengine:3000/file/datashare/test.mpg
Content-Type: video/mpeg
cache-control: no-cache
```

> Note: `Content-Type` should be the output of Detect Stream


## Get Child Content (Embedded files)


```
PUT /unpack HTTP/1.1
Host: 10.0.75.2:9998
Content-Type: application/pdf
fileUrl: http://logicappengine:3000/file/datashare/tlc_quickstart_new.pdf
cache-control: no-cache
Content-type: application/zip
```

> Note: `Content-Type` should be the output of Detect Stream.  This will also download a ZIP file with the embedded child objects

