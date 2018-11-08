# Shopify

Shopify is an e-commerce platform for online stores and retail point-of-sale systems.

It was founded in 2004 by Tobias Lutke, Daniel Weinand, and Scott Lake after attempting to open Snowdevil.

In Shopify you set almost everything in the admin section, just like Wordpress, the process is like this:

* Get a suscription on Shopify
* Choose a theme
* Add your business info in the page
* Add your bill info in the settings
* Publish your page to the public

Easy enough right?

But what happens when you want to build your website by your own in code or customize specific fields of a theme that Shopify doesn`t let you.
Well, there are some way to add code manually if you want to customize a theme that you select, this way is by [Shopify Theme Kit](https://shopify.github.io/themekit/).

## Shopify Theme Kit

Using Theme Kit will enable you to:

* Upload Themes to Multiple Environments
* Fast Uploads and Downloads
* Watch for local changes and upload automatically to Shopify
* Works on Windows, Linux and macOS

For setup a new Shopify project you just need have an account with the plan that adjusts to you, after that you need to follow the next steps:

### 1. Instalation

```
brew tap shopify/shopify
brew install themekit
```

### 2. Get the API KEY

Create a new API KEY in:

``` Apps > Manage private apps ```

### 3. Set different environments

* Create a new folder for the name of your project
* Create a file named `config.yml` and fill it with the following code of environments:

```yml
development:
  store: yourstore.myshopify.com
  password: yourapipassword
  theme_id: yourthemeid
  bucket_size: 40
  refill_rate: 2
  ignore_files:
    - "*.swp"
    - "*~"
    - "config/settings_data.json"

production:
  store: yourstore.myshopify.com
  password: yourapipassword
  theme_id: yourthemeid
  bucket_size: 40
  refill_rate: 2
  ignore_files:
    - "*.swp"
    - "*~"
    - "config/settings_data.json"
```

### 4. Set git version control

* Create a new repository for git version control

`git init`

* Create a file named `.gitignore` adding the following files to ignore in git:

```
config.yml
config/settings_data.json
```

* Create the basics branches of your repository

```
master
development
```

You can add more if you want but be sure about your git control.

### 5. Download an existing theme from Shopify

For download a theme from shopify just add the following code acording to the branch

* If you are on the **master** branch, the code will be: `theme download --env=production`
* If you are on the **development** branch, the code will be: `theme download --env=development`

_Note:_ The download will be managed by the `config.yml`, that's why so important to follow the steps

In this step, you will get all the code from the themes that you selected/created in Shopify

### 6. Push the changes from local to Shopify

For push a theme from local to Shopify just add the following code acording to the branch

* If you are on the **master** branch, the code will be: `theme deploy --env=production`
* If you are on the **development** branch, the code will be: `theme deploy --env=development`

You can also change the website locally and push to Shopify automatically by the command:

`theme watch`

This comand change the site with every modification of the local code.

## Theme Kit Usage

### See the changes in Shopify

For open and visualize the changes in local we can use this command:

* If you are on the **master** branch, the code will be: `theme open --env=production`
* If you are on the **development** branch, the code will be: `theme open --env=development`

---

## Notes:

If you don't have alternate template for product alternate templates will not show, the same goes for pages and any alternate template you want to use.

## References:

[Shopify Theme Development Workflow](https://www.youtube.com/watch?v=1xWFsYmBoX0)

[Safely Modify a Shopify Website with this Staging Workflow](https://blog.fullstackdigital.com/safely-modify-a-shopify-website-with-this-staging-workflow-d8363e01f139)