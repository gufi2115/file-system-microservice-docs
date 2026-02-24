## Microservice for efficient and secure management of static files
The architecture is based on Nginx, which is responsible for directly serving files to clients. Django REST Framework handles authorization and file upload operations. UUID, file size, MIME type, path is stored in a PostgreSQL database. Each component runs in a separate Docker container.

## Key featured

#### High-performance serving
Utilizes the X-Accel-Redirect mechanism. After successful authorization, the API returns a response containing the X-Accel-Redirect header with an internal path. Nginx then serves the file directly from disk, completely bypassing Python workers and significantly reducing their load.

#### Storage layout

Files are saved on disk using two-level sharding based on UUID (e.g. /12/34/123456...jpeg). This approach prevents performance degradation of the filesystem when storing a very large number of files.

#### Security
API access is protected using API KEY authentication.

#### Scalability
By offloading file transfer to Nginx, the service can handle high traffic with very low resource usage on the application side (minimal CPU/memory consumption of Python workers).

## Integration package
Additionally, I created a package that facilitates integration with the microservice.
[File system pack](https://pypi.org/project/filesystempack/)

## Git repositories

### Microservice
[https://github.com/gufi2115/Microservice-to-save-files](https://github.com/gufi2115/Microservice-to-save-files)

### File system pack
[https://github.com/gufi2115/filesystem-integration](https://github.com/gufi2115/filesystem-integration)

