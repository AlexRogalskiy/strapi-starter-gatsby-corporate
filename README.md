# Strapi Starter Gatsby Corporate Site

Gatsby starter for creating a corporate site with Strapi.

![screen-website](/screenshot.png)

This starter is designed for flexibility. Using it, you'll be able to manage your website content entirely in Strapi, and get a Gatsby site automatically generated. Content teams will be able to create pages and design their layout without help from developers.

This starter features:

- Pages creation within Strapi, no code necessary
- Fully flexible page structure: design the pages you want using UI Sections
- 8 UI Sections out of the box: Hero, RichText, LargeVideo, Testimonials, Pricing, BottomActions, FeatureRows, FeatureColumns
- Easy to theme with Tailwind
- Static site generation with Gatsby
- An integrated Preview Mode, to view your pages on a private URL before publishing them

## Getting started

Use our `create-strapi-starter` CLI to create your project.

```sh
# Using Yarn
yarn create strapi-starter@next my-site https://github.com/strapi/strapi-starter-gatsby-corporate

# Or using NPM
npx create-strapi-starter@next my-site https://github.com/strapi/strapi-starter-gatsby-corporate
```

The CLI will create a monorepo, install dependencies, and run your project automatically.

## Customize your corporate site

To edit this website, you'll need to run both the frontend and the backend in your development environment.

### Adding Sections

We have built sections for you, but you will likely want to add more to fit your needs. Follow these steps:

- Create a new component in Strapi in the "sections" category
- In the Content-Types Builder, open the Pages collection and check your new section on the `contentSections` field.
- Create a React component that takes a `data` prop in `/frontend/components/sections`
- To link your Strapi section to this React component, open `/frontend/components/sections.js`, and add an entry to the `sectionComponents` object.

### Custom theme

We use Tailwind CSS for styling. To modify your page's look, you can edit the theme in `/front/tailwind.config.js`. Read the [Tailwind docs](https://v1.tailwindcss.com/docs/theme) to view all the changes you can make. For example, you can change the primary color like this:

```js
const { colors } = require(`tailwindcss/defaultTheme`);

module.exports = {
  theme: {
    extend: {
      colors: {
        primary: colors.green,
      },
    },
  },
};
```

## Deploying to production

You will need to deploy the `frontend` and `backend` projects separately. Here are the docs to deploy each one:

* [Deploy Strapi](https://strapi.io/documentation/developer-docs/latest/admin-panel/deploy.html#deployment)
* [Deploy Gatsby](https://www.gatsbyjs.com/docs/deploying-and-hosting/)

Don't forget to set up your environment variables on your production apps.

Here are the required ones for the frontend:

- `GATSBY_STRAPI_URL`: URL of your Strapi backend, without trailing slash

And for the backend:

- `FRONTEND_URL`: URL of your frontend, without trailing slash

Have fun using this starter!
