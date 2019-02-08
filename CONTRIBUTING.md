# Contributing to Clay

Want to contribute to Clay? There are a few things you need to know before you start sending your pull requests or opening issues.

Here's a set of guidelines to contribute to Clay and its packages. Use your common sense, and feel free to propose changes to this document in a pull request.

#### Table of Contents

- [What Should I Know Before I Get Started?](#what-should-i-know-before-i-get-started)
	- [Clay and Packages](#clay-and-packages)
- [How Can I Contribute?](#how-can-i-contribute?)
	- [Reporting Bugs](#reporting-bugs)
	- [Your First Pull Request](#your-first-pull-request)
	- [Proposing a Change](#proposing-a-change)
	- [Sending a Pull Request](#sending-a-pull-request)
- [Style Guides](#style-guides)
	- [Git Commit Messages](#git-commit-messages)
	- [JavaScript Style Guide](#javascript-style-guide)
	- [CSS Guidelines](#css-guidelines)
	- [Documentation Style Guide](#documentation-style-guide)
- [Additional Notes](#additional-notes)
	- [Issue Labels](#issue-labels)

## What Should I Know Before I Get Started?

### Clay and Packages

The Clay repository follows the monorepo approach; the pillars of Clay, all the major components, are in this one repository.

- [clay-css](https://github.com/liferay/clay/blob/master/packages/clay-css) - Provides the colors and structure for Clay. It contains the CSS and example HTML markup for each component.
- [clay-components](https://github.com/liferay/clay/blob/master/packages) - The components that follow clay-css markup and Lexicon use cases. They are developed on Metal.js with Soy (Closure templates). Note that Clay components will be rewritten in React in version 3.0.
- [clayui.com](https://github.com/liferay/clay/blob/master/clayui.com) - Contains the source code and documentation for clayui.com.

## How Can I Contribute?

### Reporting Bugs

This section shows you how to submit an error report to Clay. Follow these guidelines so maintainers can clearly understand your report, reproduce the behavior, and find related reports.

#### Before Submitting a Bug Report

- **Check [existing issues](https://github.com/search?q=is%3Aissue+repo%3Aliferay%2Fclay)** to see if the problem has already been reported. If it has and the issue is still open, add a comment to the existing issue instead of opening a new one.

#### How Do I Submit a Good Bug Report?

Bugs are tracked as [Github issues](https://github.com/liferay/clay/issues). Create an issue, and provide the information listed below so the maintainers can reproduce the problem:

- **Use a clear and descriptive title** for the issue that identifies the problem.
- **Describe the exact steps to reproduce the problem** in as much detail as possible.
- **Describe the behavior you observed after following the steps**, and explain the problem with that behavior.
- **Explain the desired behavior you expected and why.**
- **Include screenshots and animated GIFs** if necessary.
- **If the problem is related to performance or memory**, include a [CPU profile capture](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/js-execution) with your report.
- **If the problem only occurs in a specific browser**, specify the name and version of the browser.

Provide more context by answering this question:

- **Can you reliably reproduce the issue?** If not, provide details about how frequently the problem occurs and under which conditions it normally happens.

### Your First Pull Request

If you want to contribute to this project but you don't know where to begin, issues with the "[good first issue](https://github.com/liferay/clay/labels/good%20first%20issue)" label are a great place to start.

If you decide to fix an issue, please check the comment thread first to make sure that no one else is working on a fix. If nobody is working on it at the moment, please leave a comment stating that you intend to work on it so other people don’t duplicate your effort.

### Proposing a Change

This section shows you how to propose a public API change, make non-trivial changes to the implementation, or propose something new. Follow these guidelines so maintainers can clearly understand your suggestion and your point of view.

#### Before Submitting a Suggestion for Improvement

- **Check existing suggestions** to see if the enhancement has already been suggested. If it has, add a comment to the existing issue instead of opening a new one.

#### How Do I Submit a Suggestion for Improvement?

Suggestions for enhancement or API changes are tracked as [Github issues](https://github.com/liferay/clay/issues). Create an issue in this repository and provide the following information:

- **Use a clear and descriptive title** for the issue that states your suggestion.
- **Provide a step-by-step description of the suggested enhancement** in as much detail as possible.
- **Describe the current behavior**, and explain the behavior you want to see instead and why.
- **Provide details of the impact your change will make** and how you will use it.
- **Provide the pros and cons of your change.**
- **Provide at least one alternative for your change.**

### Sending a Pull Request

This section shows you how to send a pull request. The main staff are always monitoring pull requests, so rest assured that they will review yours. Follow these guidelines so the maintainers can complete a thorough review of your request.

> Since Travis is failing on executing **a11y tests** due to out of date suid you need to execute `npm run pa11y` locally before sending any PR to verify we're following accessibility standards.

#### Before Sending a Pull Request

- Fork the repository and create your branch from **develop**.
- Run `yarn` at the root of the repository to install the project dependencies.
- Run `yarn lerna` to install the dependencies of each package and link them together.
- Run `yarn build` to build all packages.
- **If you’ve fixed a bug or added code that should be tested, add tests!**
- Run `yarn test` to ensure the test suite passes.
- If you have modified a Soy file, make sure the related tests passed by running `yarn testSoy`.
- Run `yarn format` to format your code with Prettier.
- Run `yarn lint` to make sure your code lints.
- Run `yarn mcritic` to follow the rules of Soy.

## Style Guides

### Git Commit Messages

This section shows you how to write commit messages in Clay. Follow these guidelines to help us maintain order and make it easier to locate your changes.

#### Before You Make a Commit Message

- Make sure that the problem or change you are making doesn't already exists.
- Start the commit message with the word **Fixes**, and always follow it with a reference to the issue:
	- Fixes #0 - bla bla
	- Fixes #0, #1 - bla bla

### JavaScript Style Guide

All JavaScript must adhere to the [Liferay JavaScript style guide](https://www.npmjs.com/package/eslint-config-liferay).

### CSS Guidelines

See guidelines for [contribution with CSS](https://github.com/liferay/clay/blob/develop/packages/clay-css/CONTRIBUTING.md).

### Documentation Style Guide

- Use [JSDOC](http://usejsdoc.org/) for documentation in your JavaScript code.

#### Example

```javascript
/**
 * Data to add to the element.
 * @default undefined
 * @instance
 * @memberof ClayActionsDropdown
 * @type {?object}
 */
data: Config.object()
```

## Additional Notes

### Issue Labels

This section lists the labels we use to help us organize and track the issues.

Labels are organized by categories, such as the component the problem affects, the resolution, the status...

You may want to use [Github search](https://help.github.com/articles/searching-issues-and-pull-requests/) to find groups of issues you are interested in. For example, you may be interested in [open bug issues in Clay components](https://github.com/search?q=is%3Aopen+is%3Aissue+repo%3Aliferay%2Fclay+label%3A%22comp%3A+clay-components%22+label%3A%22type%3A+bug%22&type=Issues). Use this to create more focused queries.

#### Categorization

| Category | Description |
|---|---|
| Component | Specifies the component the problem affects (e.g Clay Components, Charts...) |
| Type | Specifies the type of issue (e.g Bug...) |
| Status | Group of labels that reflect the progress of the issue |
| Resolution | Group of labels reflecting the resolution of the issue |
| Browser | Identifies the specific browser the issue affects, if applicable |

#### Labels

| Label | **`liferay/clay`** | Category | Description |
|---|---|---|---|
| RFC | [search](https://github.com/search?q=is%3Aopen+is%3Aissue+repo%3Aliferay%2Fclay+label%3Arfc) | **None** | A proposal for changes or a request for new features (similar to the RFCs that are used in [React.js](https://github.com/reactjs/rfcs/), [Ember.js](https://github.com/emberjs/rfcs), [Gatsby.js](https://github.com/gatsbyjs/rfcs), and [Rust](https://github.com/rust-lang/rfcs)) |
| Infrastructure | [search](https://github.com/search?q=is%3Aopen+is%3Aissue+repo%3Aliferay%2Fclay+label%3A%22comp%3A+infrastructure%22&type=Issues) | Component | Monorepo infrastructure, build, process automation...  |
| Clay Components | [search](https://github.com/search?q=is%3Aopen+is%3Aissue+repo%3Aliferay%2Fclay+label%3A%22comp%3A+clay-components%22&type=Issues) | Component | Clay components (e.g ClayCard, ClayLabel...) |
| Clay Charts | [search](https://github.com/search?q=is%3Aopen+is%3Aissue+repo%3Aliferay%2Fclay+label%3A%22comp%3A+clay-charts%22&type=Issues) | Component | Components of Charts in Soy or React |
| Generator Clay | [search](https://github.com/search?q=is%3Aopen+is%3Aissue+repo%3Aliferay%2Fclay+label%3A%22comp%3A+generator-clay%22&type=Issues) | Component | Our Clay Component Generator |
| Clay CSS | [search](https://github.com/search?q=is%3Aopen+is%3Aissue+repo%3Aliferay%2Fclay+label%3A%22comp%3A+clay-css%22&type=Issues) | Component | Clay CSS |
| Documentation | [search](https://github.com/search?q=is%3Aopen+is%3Aissue+repo%3Aliferay%2Fclay+label%3A%22comp%3A+documentation%22&type=Issues) | Component | Documentation in general, in clayui.com or elsewhere... |
| Accessibility | [search](https://github.com/search?q=is%3Aopen+is%3Aissue+repo%3Aliferay%2Fclay+label%3A%22comp%3A+accessibility%22&type=Issues) | Component | Accessibility issues |
| Clay site | [search](https://github.com/search?q=is%3Aopen+is%3Aissue+repo%3Aliferay%2Fclay+label%3A%22comp%3A+clayui.com%22&type=Issues) | Component | Website infrastructure or other things outside documentation that relate to the site |
| IE | [search](https://github.com/search?q=is%3Aopen+is%3Aissue+repo%3Aliferay%2Fclay+label%3A%22browser%3A+ie%22&type=Issues) | Browser | Occurs exclusively in IE browser |
| Chrome | [search](https://github.com/search?q=is%3Aopen+is%3Aissue+repo%3Aliferay%2Fclay+label%3A%22browser%3A+chrome%22&type=Issues) | Browser | Occurs exclusively in Chrome browser |
| Safari | [search](https://github.com/search?q=is%3Aopen+is%3Aissue+repo%3Aliferay%2Fclay+label%3A%22browser%3A+safari%22&type=Issues) | Browser | Occurs exclusively in Safari browser |
| Firefox | [search](https://github.com/search?q=is%3Aopen+is%3Aissue+repo%3Aliferay%2Fclay+label%3A%22browser%3A+firefox%22&type=Issues) | Browser | Occurs exclusively in Firefox browser |
| Breaking Change | [search](https://github.com/search?q=is%3Aopen+is%3Aissue+repo%3Aliferay%2Fclay+label%3A%22type%3A+breaking+change%22&type=Issues) | Type | Caused a breaking change in API or a change in behavior |
| Bug | [search](https://github.com/search?q=is%3Aopen+is%3Aissue+repo%3Aliferay%2Fclay+label%3A%22type%3A+bug%22&type=Issues) | Type | Problems with Component behavior |
| Epic | [search](https://github.com/search?q=is%3Aopen+is%3Aissue+repo%3Aliferay%2Fclay+label%3A%22type%3A+epic%22&type=Issues) | Type | Opened as an Epic (a collection of many related things to be done) |
| Discussion | [search](https://github.com/search?q=is%3Aopen+is%3Aissue+repo%3Aliferay%2Fclay+label%3A%22type%3A+discussion%22&type=Issues) | Type | A discussion of some change or a request for information |
| Enhancement | [search](https://github.com/search?q=is%3Aopen+is%3Aissue+repo%3Aliferay%2Fclay+label%3A%22type%3A+enhancement%22&type=Issues) | Type | A suggestion for improvements or refinement of code |
| Feature Request | [search](https://github.com/search?q=is%3Aopen+is%3Aissue+repo%3Aliferay%2Fclay+label%3A%22type%3A+feature+request%22&type=Issues) | Type | A suggestion for new features |
| Regression | [search](https://github.com/search?q=is%3Aopen+is%3Aissue+repo%3Aliferay%2Fclay+label%3A%22type%3A+regression%22&type=Issues) | Type | Regressions |
| Blocked | [search](https://github.com/search?q=is%3Aopen+is%3Aissue+repo%3Aliferay%2Fclay+label%3A%22status%3A+blocked%22&type=Issues) | Status | Blocked by other tasks |
| Help Wanted | [search](https://github.com/search?q=is%3Aopen+is%3Aissue+repo%3Aliferay%2Fclay+label%3A%22status%3A+help+wanted%22&type=Issues) | Status | Requires help |
| Next Release | [search](https://github.com/search?q=is%3Aopen+is%3Aissue+repo%3Aliferay%2Fclay+label%3A%22status%3A+next-release%22&type=Issues) | Status | Will be available in the next release |
| Duplicate | [search](https://github.com/search?q=is%3Aopen+is%3Aissue+repo%3Aliferay%2Fclay+label%3A%22resolution%3A+duplicate%22&type=Issues) | Resolution | Duplicates an existing issue |
| Wontfix | [search](https://github.com/search?q=is%3Aopen+is%3Aissue+repo%3Aliferay%2Fclay+label%3A%22resolution%3A+wontfix%22&type=Issues) | Resolution | Will no longer be worked on |