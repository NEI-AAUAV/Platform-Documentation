# Decisions


## TailwindCSS and DaisyUI

Problems:

https://v2.tailwindcss.com/docs/just-in-time-mode#styles-rebuild-in-an-infinite-loop

https://tailwindcss.com/docs/reusing-styles#extracting-classes-with-apply




>The most important implication of how Tailwind extracts class names is that it will only find classes that exist as complete unbroken strings in your source files.\
If you use string interpolation or concatenate partial class names together, Tailwind will not find them and therefore will not generate the corresponding CSS.\
> [Class Detection in Depth](https://tailwindcss.com/docs/content-configuration#class-detection-in-depth)



## FastAPI structure

(only api accesses crud, and only crud accesses db)
(explain schemas structure)
(explain images in dbs)

difference between commit, refresh, expire...
https://medium.com/swlh/alpine-slim-stretch-buster-jessie-bullseye-bookworm-what-are-the-differences-in-docker-62171ed4531d


use another DB istead of another schema for TESTS ?? (being done already) schema-per-service approach, tests in different DBs
```
from sqlalchemy import create_engine


engine = create_engine(conn_str, echo=False)
schema_engine = engine.execution_options(schema_translate_map={<old_schema_name>: <new_schema_name>})
NewSession = sessionmaker(bind=schema_engine)
session = NewSession()
```


## Asynchronous ORM or ODM

- should we use Asynchronous ORM or ODM?

When it comes to choosing the best database driver for MongoDB in Python, we have two popular options:

PyMongo – a MongoDB driver created by the MongoDB team for synchronous Python applications.
Motor – a MongoDB driver created for asynchronous Python applications
Despite these two options, we will be using PyMongo to query and mutate the MongoDB database.



____
https://python-gino.org/docs/en/1.1b2/explanation/why.html

even Python itself can be slower than the database operation in a stereotypical business-style CRUD-ish application, because the modern databases are so fast when the query is simple, and this kind of application usually deploys the database in a super reliable network.

The problem asyncio solves is quite different: when you need to deal with a lot of concurrent tasks, some of which may block on I/O for arbitrary time, asyncio could largely leverage the scalability with cooperative multitasking.
Since we do not expect many concurrent users, not worth it. Otherwise we would use celery.?
____
https://www.nginx.com/blog/rate-limiting-nginx/

Besides, to deal with that, rate limiting with NGINX, that throws 429, 444, or 503 errors avoid any DDoS should be enough.
____

Beanie 137 and ODMantic 100 both build on similar dependencies:

https://motor.readthedocs.io/en/stable/
Motor 45 - officially supported asynchronous Python driver for MongoDB

https://docs.pydantic.dev/
Pydantic 6 - data validation and settings management using Python type annotations


"If you are just getting started with MongoDB I would consider using Motor directly. ODMs try to improve developer experience/convenience but there is a performance and troubleshooting tradeoff given extra layers of abstraction and potential overhead."
____

Having configuration files in volumes is useful. If a change is necessary to these files, which is likely, this change can be performed on the mounted file and applied by restarting the container. If this was not done, it would be necessary to rebuild the container's image, which would take more time and resources.




## Client-side Caching

blog  https://requestmetrics.com/web-performance/http-caching
video https://www.youtube.com/watch?v=HiBDZgTNpXY




## Authentication


### IDP-UA


http://api.web.ua.pt/pt/services/universidade_de_aveiro/oauth
https://requests-oauthlib.readthedocs.io/en/latest/oauth1_workflow.html

> The IUPI (Identificador Único de Projectos e Indivíduos) makes it possible to uniquely identify the user, independently of any system in which the information is found. For users, it is perceived as an email address; for systems, an IUPI is a GUID. It is through this GUID that the communication and exchange of information regarding a user within the various systems is carried out. A user can change his profile (student, ex-student, collaborator, employee, etc.) and even his email, but never his IUPI.


## NGINX with HTTPS on development environment

https://www.baeldung.com/openssl-self-signed-cert#creating-a-private-key

Creating a Private Key

openssl genrsa -out domain.key 2048

Creating a Self-Signed Certificate

openssl req -key domain.key -new -x509 -days 365 -out domain.crt


The integration of the NGINX reverse proxy into the development environment is meant to narrow the gap between the development and production environments, thus reducing the likelihood of finding production-specific problems. 

To further bridge this gap, it is possible to implement a self-signed certificate for HTTPS in the development environment. However, this would require modifying browser settings and importing the certificate to make the browser trust it. Same thing in Postman settings. Besides, the certificate must be re-created annually, since it has a maximum expiration of one year. Given the effort required and the relative insignificance of HTTPS in the development context, which should be kept as simple as possible, this idea was left apart.




