This repo creates https://sillsdev.github.io/docu-notion-sample-site/.

The GitHub Action associated with this repo does these things:

1. uses [docu-notion](https://github.com/sillsdev/docu-notion) to grab content from [this set of Notion pages](https://hattonjohn.notion.site/docu-notion-sample-site-0e998b32da3c47edad0f62a25b49818c) and convert them into Docusaurus-friendly markdown pages,
2. runs these through [Docusaurus](https://docusaurus.io/), and then
3. publishes the result to Github Pages [here](https://sillsdev.github.io/docu-notion-sample-site/).

## Getting Started

If you already have a Docusaurus site, or are using a different system, then you should use [docu-notion](https://github.com/sillsdev/docu-notion) directly. But if you're just getting started, you can save some time be forking this repo or using it as a template for your own [Docusaurus](https://docusaurus.io/) documentation project that uses [Notion](https://notion.so) for editing.

### Instructions

1. Fork or click the "Use this template" button.

1. In Notion, duplicate [this root documentation page](https://hattonjohn.notion.site/Documentation-Template-Docusaurus-0e998b32da3c47edad0f62a25b49818c) to your own account. You can rename it anything you like.

1. In order for docu-notion to read your site via Notion's API, you need to create what Notion calls an "integration". Follow [these instructions](https://developers.notion.com/docs/getting-started) to make an integration and get your token. **Limit your integration to "READ" access**.

1. To test locally, define two environment variables:

   - DOCU_NOTION_INTEGRATION_TOKEN
   - DOCU_NOTION_SAMPLE_ROOT_PAGE (this is the ID part of the share link to your root page. It will look like `0e668b32da3c47edad0f61a25b49818b`)

1. `yarn node-pull` should pull your Notion pages into your `docs/` directory. Then do `yarn start` to test the site locally.

1. Go through `docusaurus.config.js` and customize the `title`, `base-Url`, `project-name`, `metadata`, etc.

1. To build your site using a [Github Action](https://github.com/features/actions), go to your new github repo > Settings > Secrets > Actions and add three "Repository Secrets":

   - DOCU_NOTION_INTEGRATION_TOKEN
   - DOCU_NOTION_SAMPLE_ROOT_PAGE (this is the ID part of the share link to your root page. It will look like `0e668b32da3c47edad0f61a25b49818b`)
   - PERSON_ACCESS_TOKEN_FOR_PUSH_TO_GH_PAGES_BRANCH ([instructions](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) Give it "repo" permissions).

1. Under "Actions", you should be able to manually launch a new "release" of your site.

1. For information on adding pages, see the [docu-notion](https://github.com/sillsdev/docu-notion) instructions.
