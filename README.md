# LevelUpTutorials: Pro Gatsby 2 Course


## 1: Getting Started with Gatsby JS
- Install Gatsby globally
```
npm install --global gatsby-cli
OR
npm install -g gatsby-cli
```

- Use Gatsby to start a new site
```
gatsby new <project-name>
```

- Run the site
```
gatsby develop
```

## 02: Gatsby Files Explained
- `.cache`
  - Just a cache, you don't need to worry about this
- `node_modules`
  - You know what it is
- `public`
  - This folder is what is generated by Gatsby, don't you worry 'bout it
- `src`
  - Layout
    - Contains the Site's Layout Files
  - Images
    - Image files
  - Pages
    - Contains the Site's Pages
- `.gitignore`
  - Files to ignore in this project
- `.prettierrc`
  - Prettier config file
  - Prettier auto-formats files for you
  - Linter for formatting
- `gatsby-browser.js`
- `gatsby-config.js`
  - Stores variables, stores plugins and contains meta data
- `gatsby-node.js`
  - Where we create pages in the build process
- `gatsby-ssr.js`
  - Server Side Rendering API


## 03: Creating Pages
- Create a new file in the pages folder
  - The name of the file will correlate to the route
- Within that file:
```javascript
import React from 'react'

const ComponentName = () => (
  <div>
    content
  </div>
)

export default ComponentName;
```
- To add nested files, just do `foldername/file-name.js`
- Add an `index.js` inside the `foldername` to make it the default
- Gatsby uses reach router under the hood


## 04: Working with Assets
- Import assets into JS Files
  - Gatsby will take care of caching and optimizing them for you
```javascript
import assetname from '../assets/assetname.extension';
```
- You can also create a `static` folder, which will allow you add files that won't be processed
  - You will need a `with-prefix` function from Gatsby to get this to work

## 05: Intro to GraphQL
- You can use the `graphiql` interface at localhost:8000/__graphql
Example Query:
- Open with curly brackets
- Graphiql will help autocomplete terms
- CMD+Click an item to see its properties
```
{
  site {
   siteMetadata {
   	 title
   }
  }
}
```

## 06: GraphQL Static Queries
- Static queries pull in the data we need for our site. They don't run in the compiled assets so they are super fast
- We say, `query` followed by `graphql`
- Name the query
```
  query={graphql`
    query SiteTitleQuery {
      site {
        siteMetadata {
          title
        }
      }
    }
  `}
```
- After we get the data, we render out the data with some more stuff
```
render={data => (
  <>
    <Header siteTitle={data.site.siteMetadata.title} />
    <div
      style={{
        margin: `0 auto`,
        maxWidth: 960,
        padding: `0px 1.0875rem 1.45rem`,
        paddingTop: 0,
      }}
    >
      <main>{children}</main>
      <footer>
        © {new Date().getFullYear()}, Built with
        {` `}
        <a href="https://www.gatsbyjs.org">Gatsby</a>
      </footer>
    </div>
  </>
)}
```

## 07: Plugins & Gatsby Source File System
Check out the [Gatsby Plugins](https://www.gatsbyjs.org/plugins/)

We're going to need two plugins
- `gatsby-source-filesystem`
  - This will allow us to reference Markdown files
```
npm install --save gatsby-source-filesystem
```
- `gatsby-transformer-remark`
  - This will allow us to use the Markdown files we've referenced
```
npm install --save gatsby-transformer-remark
```

This query will return all the files we have access to:
```graphql
{
  allFile {
  	edges {
      node {
        extension,
        name
      }
    }
  }
}
```

## 08: Working with Markdown
- Install the `gatsby-transformer-remark`

Getting all the Markdown Files:
```graphql
{
  allMarkdownRemark {
    edges {
      node {
        html
      }
    }
  }
}
```

## 09: Our Query in React
- We can run queries anywhere in Gatsby using `StaticQuery` and `graphql`
- The suggested way to do this is to first get it working in the Graphiql interface, then copy and paste the query into React


## 10: Improving our Query with Filtering & Sorting


## 11: Gatsby Node


## 12: Creating Pages From Markdown Files


## 13: Page Query VS Static Query


## 14: Context in Page Queries


## 15: Static Query From Scratch & Page Listing


## 16: Styled Components in Gatsby


## 17: Styling Part II


## 18: Gatsby Image


## 19: React Spring


## 20: Building Our Static Site


## 21: Hosting on Netlify


## 22: Netlify CMS


## 23: Easy Sitemaps


## 24: Progressive Web Apps with Gatsby


## 25: Where To Go Next

## Miscellaneous Notes
- `cli` = Command Line Interface
