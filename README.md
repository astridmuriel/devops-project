# Devops-project

This is the updated backend and frontend project.
 Few modifications were done to the backend and front end configuration.

## Backend

An environment variable FRONT_URL was added to the docker image and the update was made to the config file:

```
module.exports = {
    CORS_ORIGIN: process.env.FRONT_URL
}
```

This will allow the front end URL to be configurabe via an environment variable.


## Frontend

The front end was also modifed and an environment variable REACT_APP_API_URL was added to make the path to the backend configurable.

We modified the config.js file as follows:
```
export const API_URL = process.env.REACT_APP_API_URL;

export default API_URL;
```



