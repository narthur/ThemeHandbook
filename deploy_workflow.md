# Deploy Workflow

## Diagram

[![Deploy Diagram](https://github.com/SimpleUpdates/ThemeHandbook/blob/master/deploy_diagram.png?raw=true)](http://shakydraw.com/)

## Steps

### Review all themes

- Review all issues
- Review all pull requests
- Review all branches

### Prepare 2016 for deploy

- Update thumbnails in 2016
- Compare production...2016 and create a pull request if there are differences
- Request review on the PR

### Review deploy PR

This stage should be done by someone different from the person who did the previous stages.

- Pull and activate latest version of 2016
- Visually review all components in styleguide (usually at `/admin/theme/view/layout/styleguide.html`)
- Visually review all theme layouts
- Ask for any needed changes in the PR
- When satisfied, approve PR

For more information on testing, see [manual_testing.md](https://github.com/SimpleUpdates/ThemeHandbook/blob/master/manual_testing.md)

### Deploy

- Once the PR has been approved, merge 2016 into production

## Sites For Reviewing

Sites used for reviewing need to be using the 2016 branch for themes. When using one of the below sites, reinstalling the theme should update the theme with the latest commits on the remote 2016 branch.

- [acc.simpleupdates.com](https://acc.simpleupdates.com/)
- [crystalh.sites.simpleupdates.com](http://crystalh.sites.simpleupdates.com/)
