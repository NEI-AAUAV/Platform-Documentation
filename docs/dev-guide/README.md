

# Developer Guide


The repository of CrowdWire's source code can be found at: CrowdWire.

Project organization
```
.github/workflows    # The CI pipelines with github Actions.
api/                 # The backend Rest API with FastAPI.
frontend/            # The project website with ReactJS.
k8s/                 # The configuration files for deployment with Kubernets.
media_server/        # The media server for communications with Mediasoup.
README.md            # The project description and team information.
```



The API endpoints were listed and documented with Postman, an application that allows interactive API testing. It can be downloaded at https://www.getpostman.com.

After downloading it, click the button below to open the NEI API collection.

[![Run in Postman](https://run.pstmn.io/button.svg)](https://app.getpostman.com/run-collection/7af49970eb4e5516c575)

Sometimes, uploading large image files on form-data with Postman resulted in "There was an error parsing the body". This is a Postman issue, that is described [here](https://github.com/tiangolo/fastapi/issues/2401#issuecomment-735454025). A solution could be to use similar applications to Postman, like [Insomnia]( https://insomnia.rest/).






