# .github
Community Health Files for the `im-practices` organization.

Each repository within this organization will inherit these default files unless the repository has defined their own.

## Workflow Templates
The templates defined in this repository have been customized for our build processes and standards.  By including them in this repository, users can [add a workflow] to their repo by clicking a button.

The templates defined in this repository are also the source of truth for the `im-` templates in each of the Enterprise Org `.github` repos.  When a merge to main happens, the template files in this repo will be copied to the other `.github` repositories in the Enterprise.  If changes have been made to any of the `im-` template files in those organizations' `.github` repos they will be overwritten by these changes.

## Adding new Templates
If there are new templates that can be used across many organizations, please make a PR to this repository so they can be shared with each organization in the Enterprise.  

Templates that are specific to an organization should be added directly to that organization's `.github` repository.  Those template files should contain the `org-` prefix instead of the `im-` prefix.  Using the correct prefix will keep them from being overridden when this repository is synced with the others.

For detailed info around creating or modifying the templates see [Sharing workflows with your organization].

The templates in this repository fall into one of the following categories:
- Build
- Deploy
- Test
- Run
 
### Template Standards
- For new `.svg` files ensure:
  - [ ] The file contains the `im_` prefix
- For new `properties.json` files ensure:
  - [ ] The file contains the appropriate `im-<build|deploy|test|run>-` prefix
  - [ ] The `name` field has a category prefix (Build, Deploy, Test, Run)
    - This is included so templates are easier to identify when looking for workflows to add
  - [ ] The `iconName` field contains one of the [SVGs](#svgs) listed below
    - im_build
    - im_deploy
    - im_test
    - im_run
    - im_tf
    - im_checkmarx
- For new `.yml` files ensure:
  - [ ] The file contains the appropriate `im-<build|deploy|test|run>-` prefix
  - [ ] Clearly mark what needs to be customized or populated by the user
  - [ ] Avoid using default values that may be overlooked
  - [ ] Clearly state the format if something specific is required
  - [ ] If you want to use the github hosted runners use the `runs-on: ubuntu-latest` tag
  - [ ] Add a workflow code as the first line in the workflow: `# Workflow Code: UpsetBass_v1    DO NOT REMOVE`
    - When changes are made to the workflow the version should be incremented
    - Replace `UpsetBass` in the example above with your own code.  The [Random Username Generator] site can help.  The current workflows were generated using the emotions/creatures options.
  - For consistency, 
    - [ ] Ensure there are spaces between the brackets and the expression when using expression syntax
      - Expected: ${{ secrets.thing }}
      - Not expected: ${{secrets.mything}}
    - [ ] If only one label is included in the `runs-on` property, do not include brackets
      - Expected: `runs-on: ubuntu-latest`
      - Not Expected: `runs-on: [ubuntu-latest]`
    - [ ] Outside of script blocks, use single `'` instead of double `"`
    
  

[add a workflow]: https://docs.github.com/en/actions/guides/setting-up-continuous-integration-using-workflow-templates
[Sharing workflows with your organization]: https://docs.github.com/en/actions/learn-github-actions/sharing-workflows-with-your-organization
[Random Username Generator]: https://jimpix.co.uk/words/random-username-generator.asp#results