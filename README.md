# S3 Download Buildpack

A Heroku buildpack to download files from a private Amazon S3 bucket and store them in the root directory (`BUILD_DIR`) of your app.

*`BUILD_DIR` is the location of the app and `CACHE_DIR` the location the buildpack can use to cache build artifacts between builds.

## Environment Variables

The following variables are to be defined as environment variables in Heroku settings:

| Key  | Example Value |
| ------------- | ------------- |
| `S3_DOWNLOAD_BUILDPACK_AWS_ACCESS_KEY_ID` | "XXX_YYY_ZZZ" |
| `S3_DOWNLOAD_BUILDPACK_AWS_REGION` |  "us-east-1" |
| `S3_DOWNLOAD_BUILDPACK_AWS_SECRET_ACCESS_KEY` | "XXX_YYY_ZZZ" |
| `S3_DOWNLOAD_BUILDPACK_BUCKET_NAME` |  "citeab-assets" |
| `S3_DOWNLOAD_BUILDPACK_FILES` | "prefix/key1 prefix/key2" |

## Usage

#### Production

```
heroku config:add BUILDPACK_URL=https://github.com/CiteAb/s3_download_buildpack
```

#### Development

```
bash compile <build-dir> <cache-dir> <env-dir>
```

The following will install files to the current directory:
```
bash compile . . .
```


## See also

  * [Heroku Buildpack API](https://devcenter.heroku.com/articles/buildpack-api)
  * [Shell Style Guide](https://google.github.io/styleguide/shellguide.html)
