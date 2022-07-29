<img align="left" width="55%" src="https://user-images.githubusercontent.com/20285232/181688126-ad1d015c-4f67-4b00-b870-f73e59f05efa.png" width=250 height=250> 

This is an example front-end for the confere example app. It uses nextjs, react-query, tailwind, and nhost as a backend (authentication, postgres database, graphql api.) This is an example front-end for the confere example app. It uses nextjs, react-query, tailwind, and nhost as a backend (authentication, postgres database, graphql api.) This is an example front-end for the confere example app. It uses nextjs, react-query, tailwind, and nhost as a backend (authentication, postgres database, graphql api.)  

- [Getting Started](#getting-started)
- [Project Structure](#project-structure)
- [Database Schema Structure](#database-schema-structure)
- [Deploy to Nhost](#deploy-to-nhost)
  - [Creating a new Nhost Application](#creating-a-new-nhost-application)
  - [Connecting your Nhost application to a GitHub repository](#connecting-your-nhost-application-to-a-github-repository)
- [Deploying the front-end](#deploying-the-front-end)

## Getting Started

<details><summary>Steps for setting up the Nhost Backend</summary>

<p>
1. Clone the repository

```sh
git clone https://github.com/nhost/nhost
cd nhost
```

2. Install the dependencies

```sh
yarn install
```

3. Terminal 1: Start Nhost

```sh
nhost dev
```

4. Terminal 2: Start the Vue application

```sh
yarn dev
```

</p>
</details>



## Project Structure

<details><summary>Project structure walk along</summary>


Inside this folder you are going to see both the specification for the backend (Nhost) and the front-end (Vue):

```
/
├── nhost/
├── .nhost/
├── public/
│   └── favicon.ico
├── src/
│   ├── components/
│   │   └── ...vue
│   └── pages/
│       └── IndexPage.vue
└── package.json
```

</p>
</details>



## Database Schema Structure

```graphql
query ConferencesQuery {
  conferences(where: {featured: {_eq: true}}) {
    id
    name
    speakers {
      name
    }
    talks {
      name
      speaker {
        name
        bio
      }
    }
  }
}
```

## Deploy to Nhost

Nhost is the open source GraphQL backend (Firebase Alternative) and a development platform. Nhost is doing for the backend, what Netlify and Vercel are doing for the frontend. When deploying to Nhost you automatically get the following:

- Database: PostgreSQL
- Instant GraphQL API: Hasura
- Authentication: Hasura Auth
- Storage: Hasura Storage

We make it easy to build and deploy this backend using our platform that takes care of configuration, security, and performance. Things just works and scale automatically so you can focus on your product and on your business.

### Creating a new Nhost Application

First things first, we need to create a new Nhost project.

So, log in to your Nhost dashboard and click the **Create your first app** button.

![Creating an Nhost Application](https://docs.nhost.io/assets/images/create-app-step-1-64d13fc87fac1d0989da25857e1c3811.png)

Next, give your new Nhost app a name, select a geographic region for your Nhost services and click Create App.

![Creating an Nhost Application](https://docs.nhost.io/assets/images/create-app-step-2-823c33a87887cbe28da98a85219dcc59.png)

After a few seconds, you should get a PostgreSQL database, a GraphQL API with Hasura, file storage, and authentication set up.

### Connecting your Nhost application to a GitHub repository

Through the Nhost console interface you can connect this template to your Nhost application. When you do this, your application will be automatically deployed and any following updates you push to your code will also be automatically be deployed.

<details><summary>Steps to automatically connect this repository to your Nhost application</summary>

1. Fork/clone this repository to your GitHub account.

2. Provide the require permissions to select this repository to the official Nhost GitHub application.

3. Find your repository on the Nhost Console & connect it:

<p align="center" width="100%">
    <img width="55%" height="80%" src="https://user-images.githubusercontent.com/20285232/181070306-851187ca-6595-4cdc-b458-b62b479479db.png"> 
</p>


4. Once connected, the application will automatically deploy.

<p align="center" width="100%" height="100%">
    <img width="55%" height="500px" src="https://user-images.githubusercontent.com/20285232/181070624-f12571a4-6b77-4a2f-acab-9e156306b392.png"> 
</p>

5. Add changes to your application. Any changes you push to your repository will also be automatically be deployed (you can see your deployments on the "Deployments" section of the console)


<p align="center" width="100%">
    <img width="55%" height="500px" src="https://user-images.githubusercontent.com/20285232/181070633-c3c67e94-981c-4574-954b-c643448f387e.png"> 
</p>

</p>
</details>

## Deploying the front-end

