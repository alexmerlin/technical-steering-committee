# Next Technical Steering Committee Meeting Agenda

- Date: 2021-12-06
- Time: 19:00 UTC

Please file pull requests to add, or discuss items to add, to the agenda.

## Items to Discuss

- Reusable GitHub Actions workflows (https://github.blog/2021-11-29-github-actions-reusable-workflows-is-generally-available/) are now generally available: is it something that we can somehow use?
    * we could simplify our CI setup even further, hiding the "matrix" that we generate
    * we could make the automatic-releases workflow a bit smaller to integrate
    * we could introduce some automations for tweeting/publishing releases to outside the organization
    * we could introduce "branch cleanup" actions that delete branches for which our maintenance policy no longer covers support
    * we could automate dependency upgrades
- Automating dependency upgrades
    * Automating composer dependencies upgrades with @dependabot, and the noise it would cause in email notifications. It is necessary, but a solution that doesn't overwhelm maintainer inboxes is somehow needed.
    * Automating patches to upgrade PHP versions? That would save us quite a lot of work in 2022.
- Is “laminas-db” abandoned?
    * We have 15 opened pull request and 11 opened issues.
    * We have 3 non active mainteners on "laminas-db" project.
    * Last merge was 4 months ago. 
    * Version 3 is not developed since 31 Dec 2019.
    * Unit tests have errors. 
    Volunteer developers cannot complete the quest with CI on github and stop making contributions.
    For example, in pull request #232, the comment was changed, but the test failed!
    Give us local instrument for run tests (the best is Docker images on official repository).
    * Tests for Oracle is not support on CI.
