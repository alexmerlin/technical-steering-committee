# Next Technical Steering Committee Meeting Agenda

- Date: 2022-03-07
- Time: 19:00 UTC

Please file pull requests to add, or discuss items to add, to the agenda.

## Items to Discuss

- Adopting a code coverage tool: I'm a big fan of using CodeCov in my work/personal projects mainly because it fails CI if project or patch coverage declines. I accept the coverage is not the best quality metric in the world, but the PR comments from CodeCov _(Which I'm most familiar with)_ provide pretty swift feedback on submitted code… I'm fairly confident that you can install the CodeCov app org wide and a token is not required for upload with public repos, theoretically meaning that the matrix action could be updated to collect and upload coverage for all repos without any adjustment on a per-repository basis.
- Phone number validation as performed by `laminas-I18n` attracts not-too-infrequent issues around correct validation of phone numbers. This was noted in [`laminas-I18n`#74](https://github.com/laminas/laminas-i18n/issues/74). I've put together an initial component at [`gsteel/laminas-i18n-phone-number`](https://github.com/gsteel/laminas-i18n-phone-number), that leverages [`giggsey/libphonenumber-for-php`](https://github.com/giggsey/libphonenumber-for-php) to perform validation and filtering _(Potentially useful view helpers too)_, for possible addition to the Laminas org.<br>From a maintenance perspective, the relatively frequent meta-data updates provided by the `libphonenumber` port should keep it to a minimum 🤞.
- `laminas-api-tools/api-tools-oauth2` contains hard dependency with `bshaffer/oauth2-server-php` which looks abandoned. What we can do with that?
  - Fork unmaintained repository and develop under Laminas.
  - Change server implementation (e.g. `league/oauth2-server`).
  - Create abstraction for oauth2 server and create satellite repositories with desired implementation.
  
  First option looks the fastest and easy way to start (updating PHP support to 8.1, fixing any incompatibility and security issues), however in long run use something external is more reasonable. Make abstraction will protect us from situations like now.
- I've filed an RFC for consideration in `laminas-view` [#149](https://github.com/laminas/laminas-view/issues/149) for an overall simplification of `laminas-view` that would include significant BC breaks for a number of related projects, possibly requiring new majors in those components too, for example `laminas-form` and `i18n`. By way of example, I've opened a pull in `i18n` [#75](https://github.com/laminas/laminas-i18n/pull/75) that provides incremental changes to move towards compatibility with a 3.0 release of view.
 <br>The overall goal of this 'simplification' is to make view as stateless as possible and appropriate for use outside of MVC, on the cli, rendering email message views, running under Open/Swoole/React/Whatever without hidden state gotchas.
