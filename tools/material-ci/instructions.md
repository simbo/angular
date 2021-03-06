### Unit tests for Angular CDK/Material
The unit tests from angular/material2 run on CircleCI under the `material-unit-tests` job.
Known failing tests are skipped based on the blacklist in
`tools/material-ci/angular_material_test_blacklist.js`. Whenever the root cause of a known failure
is identified, the `notes` field for the corresponding tests should be updated. Whenever a failure
is resolved, the corresponding tests should be removed from the blacklist.

### Debugging
To debug a failure, you need to work against the angular/material2 repo:
1. Clone `angular/material2`
2. Checkout the `ivy-2019` branch
3. Run `yarn`
4. Run `scripts/ivy/install-angular.sh path/to/local/angular/repo`
5. Run `gulp test`

### Regenerating the blacklist
If a problem has been fixed, you can regenerate the blacklist by:
1. Clone `angular/material2`
2. Checkout the `ivy-2019` branch
3. Run `yarn`
4. Run `scripts/ivy/install-angular.sh path/to/local/angular/repo`
5. Run `gulp test`. Let it finish. It will take a few minutes.
6. Run `scripts/ivy/generate-blacklist.js`
7. Copy the new blacklist from `dist/angular_material_test_blacklist.js`
