# A Guide for Open Source Maintainers: Engaging Students Effectively

This guide is geared towards helping open source maintainers in academic settings to better engage with students who might be interested to contribute to an open source project.

## 1. Write Clear Contributor Guidelines

The single most important thing you can do before advertising your project to students is make it easy to understand *how* to contribute and what contributions are welcome for your project.  This information typically goes in your `CONTRIBUTING.md` at the root of your repository.

Ideally your contributor documentation should cover:

- **How to set up a development environment:** the needed steps to be able to build and test your project's codebase
- **The contribution workflow:** how to fork the codebase, open a pull request, and what to expect during review
- **Code style and standards:** specify what linting or style guide requirements are needed to contribute to this project
- **How to communicate:** where questions go (GitHub Discussions, Slack, Discord, mailing list) and how fast you typically respond to any questions/issues posted on these channels
- **How the codebase is organized:** a brief map of what lives where and why
- **A Code of Conduct:** how the community members are expected to behave as both contributors and reviewers
- **GenAI policies for PRs:** increasingly, students and contributors will be using GenAI tools to contribute to your project. Note how you plan to review these contributions and if there are any restrictions on using GenAI to contribute to your codebase.
    - You may want to combine any policies for GenAI with policies on what you consider to be an appropriate PR. 

GitHub provides excellent documentation on [setting up contributing guidelines](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/setting-guidelines-for-repository-contributors) and Nadia Asparouhova has created an [excellent contributing guide template](github.com/nayafia/contributing-template) that you can copy and customize to quickly get started.

> [!TIP]  
> An incomplete CONTRIBUTING guide is better than a non-existent one!

## 2. Be Explicit About What Kind of Engagement You're Offering Students

Students come to open source projects with very different goals: some need academic credit, some want a paid position, and some are just looking to build their portfolio. Be upfront about the engagement model  ideally in your README or a dedicated "Work With Us" section  and distinguish clearly between:

- **Volunteer / community contributions:** The student contributes on their own time with no compensation or formal academic arrangement. This is the default model for most open source, but it is helpful to note this explicitly for your project's contributors.
- **For-credit research**: The student registers for an independent study course, VIP team, or similar course (e.g., a 2699/4699 or 89xx at Georgia Tech) and their work counts toward their degree. This typically requires a faculty advisor and a defined scope of work agreed upon before the semester starts.
    - It is helpful to provide steps needed to register and any selection process used for students. 
- **Paid positions:** Paid positions require a clear description of hours, compensation, duration, and deliverables.


## 3. Create Good First Issues

One of the most effective things you can do to attract student contributors is to maintain a set of well-scoped, clearly documented issues tagged `good first issue`. These serve as a structured entry point  students can see exactly what needs doing, understand the scope, and attempt a real contribution without having to understand the entire codebase first.

A good first issue should include:

- **A clear problem statement** what is wrong or missing, described in plain language.
- **Relevant context:**  links to the relevant file(s), function(s), or documentation, and a brief explanation of why this matters to the project.
- **Acceptance criteria:**  what does "done" look like? What should a reviewer be able to verify?
- **Suggested approach:**  not a solution, but a hint at where to look or what to try. This is especially helpful for students who are new to the domain.
- **Estimated difficulty:**  a rough sense of whether this requires 1 hour or 1 week of work.

Keep your `good first issue` backlog fresh. Stale issues that have sat untouched for months or that reference outdated code may actively discourage new contributors.

## 4. Adopt Good Software Engineering Practices: Tests and CI/CD

If your codebase lacks tests and automated checks, you are likely making your own review burden heavier and are definitely making contributing a more frustrating process for students. Having a good test suite allows you to ask students to fix common issues on their own before requesting review by you or other maintainers. Suggestions to implement good testing infrastructure includes:

- **Maintain a test suite:** that covers your core functionality. Even a modest set of unit and integration tests is far better than none. Ideally, you should document how to run the tests locally in your `CONTRIBUTING.md` or a related testing document.
- **Configure CI/CD:** Use GitHub Actions (or an appropriate alternative) to automatically run your tests, linter, and any other checks on every pull request. This way, a student's PR either passes or fails on objective criteria before you ever look at it, and they can fix obvious issues themselves.
- **Use a linter and formatter:** and enforce them in CI. This can reduce review time and discussion of style-related issues with PRs.
- **Require pull request descriptions:**  PR templates can prompt contributors to explain what they changed and why, link to the relevant issue, and confirm they've run the tests.


## 5. Use GitHub Templates to Structure Contributions

One underappreciated tool for OSS maintainers engaging student contributors is GitHub's template system, which lets you pre-populate the structure of issues and pull requests so that student contributors know exactly what information to provide.

Related research by [Smith et al. "A Software Engineering Capstone Course Facilitated By GitHub Templates](https://arxiv.org/abs/2410.12114) found that providing teams with a GitHub template containing predefined folder structures, document templates, and issue templates helped students spread their work out over the semester (rather than rushing at the end of the semester), and this structure contributed to more equitable participation among team members. 

GitHub supports two kinds of templates that are relevant for student engagement:

**Issue templates** (stored in `.github/ISSUE_TEMPLATE/`) allow you to create structured forms for bug reports and feature requests. 

For student engagement, you can also create a specific "Student Contribution" issue template to be used for recruiting and onboarding students. This  that prompts students to describe their background, the course or program they would be contributing through, and their availability for specific tasks with the project.

**Pull request templates** (stored in `.github/pull_request_template.md`) pre-populate the PR description with prompts like:

- What issue does this address?
- What changes did you make and why?
- How did you test this?
- Are there any known limitations?

Pull request templates help to produce better pull requests that are easier to review, and they reinforce professional norms and conduct around reviews. PR template responses can also be useful for documenting student work as part of a credit-based OSS project.

See GitHub's documentation on [issue and PR templates](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests) for more information.

## Advertise your Project!

You can also list your project on the [OSS Project Explorer](https://ospo.cc.gatech.edu/) and the [LibreTech Collective's LibreLinker](https://librelinker.us/) as low-effort ways to increase your visibility with students actively looking for projects to contribute to. Student research programs are also a great way to engage with student contributors.
