# package-manager-as-a-service
Package Manager As A Service

Any type of  "package" is supported, including: jar, zip, aar, apk, ios, app, msi, deb, etc..



## Features

- Search by type, popularity, keywords
- Easy upload and download (uses REST)
- Easy pricing:
  - $0 (free) up to 2 packages (up to 100MB each).
  - $4/month for each additional set of 5 packages. (covers expenses for server storage/bandwidth/availability).
  - *A package is defined as a unique name and all versions of it. Rates may rise in the future, but you can lock in your lower prices now.



## Usage

- Via REST:

        anonsage.com/pmaas/api/v1/upload
        anonsage.com/pmaas/api/v1/download

- Via command line:

        pmaas upload config.json my-package.apk
        pmaas download my-group:my-package-name:version

- Via GUI: Visit [anonsage.com/pmaas](http://anonsage.com/pmaas)



## Uploading

- Requires GitHub account to upload package.
- Each uploaded package should have a config file with it, with a minimal of group, name, description, and version fields. A dependency field is optional.

        // config.yaml
        group: com.example.platform
        name: my-awesome-package
        description: An example description
        version: 1.0.0
        dependency:
            com.anonsage.java:simple-utils:0.3
            com.squareup.okhttp3:okhttp:3.0.0-RC1



## TODO 

- Allow removal of uploaded packages if one of the following:
  - are less than a day old
  - have less than 10(?) downloads
