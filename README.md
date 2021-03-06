# README: Overview Documentation Repository

This README explains the user cases, source file organization, and procedures for building the Blockstack documentation.  You can find the documentation at https://docs.blockstack.com

## Use Cases

Blockstack is a ecosystem build around a platform. There are several types of users to support with the documentation. Types are exist when they can operate within a vertical of the ecosystem.  These are the users that can appear within this ecosystem and that the docs must support.

<table>
  <tr>
    <th>Users</th>
    <th>Description</th>
  </tr>
  <tr>
    <th>STX holders</th>
    <td>Users who have purchased STX and who use our wallet to move STX holdings. These users want to know about Blockstack as a company and STX as an investment token. They have a Blockstack identity, they use the Blockstack wallet, and may also use the Blockstack explorer.</td>
  </tr>
  <tr>
    <th>DApp users</th>
    <td>Users who make use of applications built on the Blockstack platform. These users have a Blockstack identity and typically use the Blockstack Browser at some point.</td>
  </tr>
  <tr>
    <th>Dapp developers</th>
    <td>Users who develop applications on the Blockstack platform.</td>
  </tr>
  <tr>
    <th>Hub Providers</th>
    <td>Users who sell or maintain a Gai services are hub providers.  These users may be more devops user types as opposed to developers.</td>
  </tr>
  <tr>
    <th>Core service programmers</th>
    <td>These are users that run Stacks node or who write Clarity contracts. These are also users who build wallets or explorers into the Blockstack platform.</td>
  </tr>
</table>

Finally, a key user set but seldom mentioned for any company docs is the company employees. These users are expected to make use of the documentation when onboarding or to support other users.

## Documentation backend

Our documentation is written in Markdown (`.md`), built using [Jekyll](https://jekyllrb.com/), and deployed to a Netlify server. Serving the content from Netlify allows us to use functionality (plugins/javascript) not supported with standard GitHub pages. 

Blockstack versions it source files in a public GitHub repo (duh :smile). You can submit changes by cloning, forking, and submitting a pull request. You can also make use of the **Edit this page on GitHub** link from any https://docs.blockstack.org page.

Some content is single sourced. Modifying single source content requires an understanding of that concept, how it works with Liquid tags, and the organization of this repo's source files.

[UIKit](https://getuikit.com/docs/introduction) provides the documentation theme. There is explicit use of HTML plus UIKit components directly in files where needed for special layouts. And there is use of CSV and JSON source files transformed with [Liquid template language](https://help.shopify.com/en/themes/liquid) to produce reference content.

## How the Source Files are Organized

Directories that contain information used to build content.

<table>
  <tr>
    <th>Directory</th>
    <th>Purpose</th>
     <th>Technical Repo(s)</th>
  </tr>
  <tr>
    <td>_android</td>
    <td>SDK tutorial. Part of the <a href="https://github.com/blockstack/docs.blockstack/blob/master/_data/navigation_learn.yml">developer menu</a>.</td>
   <td><a href="https://github.com/blockstack/blockstack-android">https://github.com/blockstack/blockstack-android</a></td>
  </tr>
  <tr>
    <td>_browser</td>
    <td>Information for end-users about our identity, Storage, and using the browser. There are also three of the original tutorials in there. User docs controlled by in the the <a href="https://github.com/blockstack/docs.blockstack/blob/master/_data/navigation_usenew.yml">user menu</a>. The three tutorials that appear in the <a href="https://github.com/blockstack/docs.blockstack/blob/master/_data/navigation_learn.yml">developer menu</a> There is an <a href="https://github.com/blockstack/docs.blockstack/issues/501" target="_blank">outstanding issue</a> to move these.</td>
   <td><a href="https://github.com/blockstack/blockstack-browser">https://github.com/blockstack/blockstack-browser</a></td>
  </tr>
  <tr>
    <td>_common</td>
    <td>Contains several shell files that redirect to our reference documentation sites such as Javascript, IOS, and so forth.  The reference docs are linked from the developer, core, and Gaia menus.</td>
    <td>Each of these references are generated by their respective repos, core.blockstack.org from <code>blockstack-core</code>, Javascript docs from the <code>blockstack.js</code> and so forth.</td>
  </tr>
  <tr>
    <td>_core</td>
    <td>Information for wallet, blockchain, or Clarity developers -- including Atlas, BNS, and so forth. <b>This content STILL needs to be synced with the master docs subdirectory in <a href="https://github.com/blockstack/blockstack-core/tree/master/docs" target="_blank">blockstack-core</a>.</b></td>
    <td> <a href="https://github.com/blockstack/blockstack-core/tree/master/docs" target="_blank">blockstack-core</a></td>
  </tr>
  <tr>
    <td>_develop</td>
    <td>Information for application developers covers using the Javascript library, our mobile SDKs, and the concepts hat support them. Navigation controlled by <a href="https://github.com/blockstack/docs.blockstack/blob/master/_data/navigation_learn.yml">developer menu</a> </td>
    <td>This information was never associated with a single repo. Much of it does rely heavily on <a href="https://github.com/blockstack/blockstack.js">https://github.com/blockstack/blockstack.js</a>.</td>
  </tr>
    <tr>
    <td>_faqs</td>
    <td>Contains files for single-sourcing all the FAQs. The Blockstack docs has a single page that <a href="https://docs.blockstack.org/faqs/allfaqs" target="_blank">lists all the faqs</a>; then several pages in different sections re-use this information. See the FAQs section below for detail about how these files figure into FAQS.</td>
    <td>Not related to repo.</td>
  </tr>
  <tr>
  <td>_includes</td>
    <td>Information reused (markdown or html) in many places, common html used in pages and notes. </td>
    <td>These files don't correspond to a repository.</td>
  </tr>
    <tr>
    <td>_ios</td>
    <td>SDK tutorial. Part of the <a href="https://github.com/blockstack/docs.blockstack/blob/master/_data/navigation_learn.yml">developer menu</a>.</td>
    <td><a href="https://github.com/blockstack/blockstack-ios">https://github.com/blockstack/blockstack-ios</a></td>
  </tr>
  <tr>
    <td>_org</td>
    <td>Information for Stacks holders and people curious about what Blockstack does. Appear in the the <a href="https://github.com/blockstack/docs.blockstack/blob/master/_data/navigation_org.yml">organization menu</a></td>
    <td>Not associated with any repository.</td>
  <tr>
    <td>_storage</td>
    <td>Information for developers using storage in their apps or creating Gaia servers. Appear in the the <a href="https://github.com/blockstack/docs.blockstack/blob/master/_data/navigation_storage.yml">storage menu</a></td>
       <td><a href="https://github.com/blockstack/blockstack-gaia">https://github.com/blockstack/blockstack-gaia</a></td>
  </tr>
  </table>

These are the other directories in the site structure:

<table>
  <tr>
    <th>Directory</th>
    <th>Purpose</th>
  </tr>
  <tr>
    <th>_data</th>
    <td>JSON source files for the FAQS, CLI, and clarity reference. Menu configurations YAML files. The CSV file with the glossary. </td>
  </tr>
<tr>
    <th>_layouts</th>
    <td>Layouts for various pages. The community layout is significantly different from the other layouts.</td>
</tr>
   <tr>
    <th>_plugins</th>
    <td>Code files for plugins.</td>
  </tr> 
  <tr>
    <th>_sass</th>
    <td>Style folder including customizations.</td>
  </tr>
 <tr>
    <th>assets</th>
    <td>Support for the docs templates.</td>
  </tr>
  </table>



## Building the documentation source for display

If you are making significant changes to the documentation, you should build and view the entire set locally before submitting a PR.

## Run locally

To run locally:

1. Install Jekyll into your workstation environment
2. Build and serve locally.

   ```
   bundle exec jekyll serve --config _config.yml,staticman.yml --livereload
   ```

   Use this format to turn on production features:

   ```
   JEKYLL_ENV=production bundle exec jekyll serve --config _config.yml
   ```
## Test a Deploy with Surge

You can also do a test deploy using a tool like [Surge](https://surge.sh/).

```
cd _site
surge
```

Make sure you delete the deployed Surge domain when you are done. Using the `teardown` command.

```
  surge – single command web publishing. (v0.21.3)

  Usage:
    surge <project> <domain>

  Options:
    -a, --add           adds user to list of collaborators (email address)
    -r, --remove        removes user from list of collaborators (email address)
    -V, --version       show the version number
    -h, --help          show this help message

  Additional commands:
    surge whoami        show who you are logged in as
    surge logout        expire local token
    surge login         only performs authentication step
    surge list          list all domains you have access to
    surge teardown      tear down a published project
    surge plan          set account plan

  Guides:
    Getting started     surge.sh/help/getting-started-with-surge
    Custom domains      surge.sh/help/adding-a-custom-domain
    Additional help     surge.sh/help

  When in doubt, run surge from within your project directory.
  ```

## Deployment of the site

The documentation is deployed to Netlify using the following command:

    ```
    JEKYLL_ENV=production bundle exec jekyll build --config _config.yml

## Generated documentation

### To generate the CLI json manually

The `_data/cliRef.json` file is generated from the `blockstack-cli` subcommand `docs`. This data file is consumed by the `_includes/commandline.md` file which is used to serve up the reference.  

1. Install the latest version of the cli according to the instructions at: https://github.com/blockstack/cli-blockstack

2. Generate the json for the cli in the `docs.blockstack` repo.

   ```
   $ blockstack-cli docs | python -m json.tool > _data/cliRef.json 
   ```

3. Make sure the generated docs are clean by building the documentation.

   If you run into any problem in the generation usually it results from a problem in the repo. You can make a pull request back to the repo to fix anything.

### Clarity Reference

As of 8/12/19 Clarity is in the [develop](https://github.com/blockstack/blockstack-core/tree/develop) branch of core.  You can build the Clarity command line from the Docker image. `core/src/vm/docs/mod.rs`


1. Pull the latest developer preview from the Docker Hub.

   ```
   $ docker pull blockstack/blockstack-core:clarity-developer-preview
   ```

2. Build the lastest JSON.

   ```
   docker run -it blockstack/blockstack-core:clarity-developer-preview blockstack-core docgen | jsonpp > ~/repos/docs.blockstack/_data/clarityRef.json
   ```

3. Build the documentation and verify the Clarity reference is building correctly.

4. Make changes in core
5. Build the docker image
6. Run doc gen with the new image

    ```
   $ docker run --name docsbuild -it blockstack-test blockstack-core docgen | jsonpp > ~/repos/docs.blockstack/_data/clarityRef.json
    ```
    
    This generates the JSON source files which are consumed through Liquid templates into markdown.

7. Rebuild the documentation site with Jekyll.

8. Review the changes in the Clarity documentation to ensure that no breaking changes were introduced through code changes.

9. If you find the documentation is no longer formatting correctly or there are errors in the reference, create a PR against the `blockstack-core` repo.

### View and test the clarity cli

You can view [the source code](https://github.com/blockstack/blockstack-core/blob/develop/src/clarity.rs).

1. Pull the Stacks Node clarity-developer-preview image from Docker Hub.

   ```bash
    $ docker pull blockstack/blockstack-core:clarity-developer-preview
   ```

2. Start the Stacks Node test environment with a Bash shell.

    ```bash
    $ docker run -it -v $HOME/blockstack-dev-data:/data/ blockstack/blockstack-core:clarity-developer-preview bash
    ```

    The command launches a container with the Clarity test environment and opens a bash shell into the container.

3. Run the clarity-cli in the shell.

    ```bash
    root@5b9798633251:/src/blockstack-core# clarity-cli
    Usage: clarity-cli [command]
    where command is one of:

    initialize         to initialize a local VM state database.
    mine_block         to simulated mining a new block.
    get_block_height   to print the simulated block height.
    check              to typecheck a potential contract definition.
    launch             to launch a initialize a new contract in the local state database.
    eval               to evaluate (in read-only mode) a program in a given contract context.
    eval_raw           to typecheck and evaluate an expression without a contract or database context.
    repl               to typecheck and evaluate expressions in a stdin/stdout loop.
    execute            to execute a public function of a defined contract.
    generate_address   to generate a random Stacks public address for testing purposes.
    ```

## Understand how the shared FAQs work

The FAQ system servers single-sourced content that support the FAQs that appear in blockstack.org, and stackstoken.com site. We have FAQs that fall into these categories:

* general 
* appusers
* dappdevs
* coredevs
* opensource
* miscquest
* wallet  (Wallet users)
* tokens (Stacks owners)

FAQs are usually written internally by a team that are unfamiliar with markdown or HTML used in websites. So, FAQs are produced using this process:

1. Draft new or revised FAQs in a Google or Paper document.
2. Review the drafts and approve them.
3. Convert the FAQ document to HTML.
4. Strip out the unnecessary codes such as `id` or `class` designations. 
   This leaves behind plain html.
5. Add the new FAQs to the `_data/theFAQS.json` file.
   Currently this is manually done through cut and paste. 
6. Copy the JSON for `appminers` categories to the `_data/appFAQ.json` file.
7. Run the Jekyll build and verify the content builds correctly by viewing this `LOCAL_HOST/faqs/allfaqs`
8. Push your changes to the site and redeploy.

 Single sourcing the content ensures that FAQs are the same regardless of where and on which property they appear in. These source files play a role in the FAQ single-sourcing layout:

<table>
  <tr>
    <th>File </th>
    <th>Contains</th>
    <th>Purpose</th>
  </tr>
  <tr>
    <td>_faqs/allfaqs.json</td>
    <td>Liquid to generate JSON from theFAQS.json</td>
    <td>Serves up the FAQs that are consumed by the blockstack.org and stackstoken.com sites.</td>
  </tr>
  <tr>
    <td>_faqs/allFAQs.md</td>
    <td>Liquid and headings.</td>
    <td>Reads the _data/theFAQs.json and produces a Markdown file for display in our site.</td>
  </tr>
  <tr>
    <td>_data/theFAQs.json</td>
    <td>JSON for the FAQS.</td>
    <td>Source file for all the FAQs.</td>
  </tr>
</table>


# Technology Reference

* [UIKit](https://getuikit.com/docs/grid)
* [Liquid templates](https://shopify.github.io/liquid/)
