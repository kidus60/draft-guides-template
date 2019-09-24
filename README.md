## Contributing to the guides
Each guide resides in its own repository and is dynamically pulled into kabanero.io via the build process. The content of the guide can be written in HTML, markdown, or AsciiDoc formats- AsciiDoc is preferred. The following front matter variables must be set:
```
---
permalink: /guides/repository_name/
---
- layout: guide
- duration: `time required to complete the guide`
- description: `one line description of the guide`
- tags: `(optional) array of tags associated with the guide`
```
The naming convention for `permalink` is `/guide/` followed by the GitHub repository name (do not include `guide-`)
   * For example, the appropriate `permalink` for https://github.com/kabanero-io/guide-overview/ would be `/guides/overview/`
   * This eliminates guide URL conflicts for guides as GitHub won't allow two repositories with the same name.

`layout` could also be `guide-multipane` which renders that code column to show code on the side.

To get started open an issue to get a repository in the kabanero-io github org created for your guide. Make sure `draft-guide-` is appended to the beginning of the repo name. `draft-` ensures it will not get published to the site. `guide-` ensures our build process will pull in the guide during build.

### Images for Guides

If you want to add images to your guide you can put them in your guide repository.

* Image Location
   * Create a dir in your guide repositoy called `assets` and put them in there. 
      * These images get copied over to the sites `/img/guides/` dir during build. 

* Image Naming
   * You should include the name of your guide in the name your image to prevent image naming conflicts from other guide repositories.
   
* Image Reference
   * You can reference the image in your AsciiDoc file like the following example:
      * `image::/img/guide/name_of_your_image.png[link="/img/guide/name_of_your_image.png" alt="Your image alt text"]`

# Render a Guide locally

Once you have your local development environment setup you can render guides as your write them.

## Prereqs
* [Local development setup](https://github.com/kabanero-io/kabanero-website/blob/master/CONTRIBUTING.md#local-development-setup)

## Render your guide

1. Create a new dir called `guides` under `src/main/content/`
1. Inside the new `guides` dir, make a new folder called `guide-name_of_your_guide`
1. Create the `README.adoc` in that newly created folder and place your content in there.
1. Start your local dev server and go to `https://localhost:4000/guides` to see all the guides rendered.


