# beaker-qa-i18n helper

- [beaker-qa-i18n helper](#beaker-qa-i18n-helper)
  - [Examples](#examples)
  - [Releasing](#releasing)

Methods to assist in i18n testing

## Examples

   Example: iterates through array of strings of length 10, testing all special characters according to the block

   ```Ruby
   test_i18n_strings(10) { |test_string|
     # Enter data
     create_user("User#{test_string})
     # Validate data
     verify_user_name_exists("User#{test_string}")
   }
   ```

## Releasing

Open a release prep PR and run the release action:

1. Bump the "version" parameter in `lib/beaker-abs/version.rb` appropriately based merged pull requests since the last release.
2. Run `./release-prep` to update `Gemfile.lock` and `CHANGELOG.md`.
3. Commit and push changes to a new branch, then open a pull request against `main` and be sure to add the "maintenance" label.
4. After the pull request is approved and merged, then navigate to Actions --> Release Action --> run workflow --> Branch: main --> Run workflow.
