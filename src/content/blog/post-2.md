---
title: 'Code Reviews'
publishDate: '2022-07-19'
excerpt: 'Code reviews ensure correctness, collaboration, and consistency while fostering trust and knowledge sharing among teams—key to scalable software.'
tags:
  - Developemnt Process
seo:
  image:
    src: '/post-2.jpg'
    alt: Half open laptop on a desk
---

![Half open laptop on a desk](/post-2.jpg)

> TL;DRs


Code reviews enhance code quality, ensure correctness, and foster collaboration. They balance engineering velocity with benefits like consistency, knowledge sharing, and team trust. Best practices include clear communication, small changes, and automation to streamline the process.

## Introduction

Code review is a process in which code is audited by the author's peers. It acts as a checkpoint before that piece of code merged into the codebase.

Code review not only has obvious benefits such like discovering early bugs, verify legitmacy of the implementation, qucik demo. It also has subtles effects like collabration within the platform, aligning the expectations, encourgage open healthy disucussions, build relationship and trust with teamates.

<!--
- Start with a clear and gripping headline to stir up interest
- Tell your readers what they will gain or learn from your article
- Include number from statistics to build trust
-->

## Main Concept

### Code Review Workflow

Different organzation have different take on the code review process and they can happen in various stages of software development. Some might even have highly automated continuous integration flow with pre-commit checks, linting systems, commit semantics, test runners, build preview before getting to the inital step describe below. This is a typical workflow from my own experience:

1. Workspace - Author made a PR/MR and pushed code to a code management tool like Github or Gitlab
2. Author - Typically there's will be some sort of automation flows that validate if the codebase indeed works with your changes applied. Then author will verify the changes diff and made self correction base on the changes.
3. Reviewer - Once it has passed the self-review process, the MR/PR will be notified to a broader pool of developers or/and assigned to the owner of the piece of the software. They will be making some generic informational comments or sometimes explicit resolution.
4. Amend - The disucussions might go back and fourth on the code review tool until a concense is made, or if changes are applied.
5. Approve - When the reviewers are staisfyied with the latest state of the logic, they will mark this PR/MR with an approved (or looks good to me) status
6. Commit - It is now ready to move to next stage (passing to QA or merge to master) after all comments are resolved and changes are approved by all reviewer

You may wonder "my code is working", whats the point of all this hassel when trying to get something up and running. In the following section I will be explaining the philsophy behind this incentive.

### Whats the Point of Code Review

Now we have looked at the typical code review process, lets explore why this is an important principle to scaling softwares.

Frist, we need to acknowledge that "code is a liability", what it provide might be an asset, but down to its core, code is simply a mainenance task for someone in the future. Much like a car, it will take you from point A to B but it actually showed up a liability on your account. Or like the fuel that an rocket carries, it has tremedous weight, but it is necessary for it to reach space.

There's a three deimensional complexity when a certain peice of code changed:

1. On a team level

- It could be comprehened by your peers
- It's doing whats it supposed to do
- A team/squad member would often be involvd in this process

2. On a systemic level

- It is appropriate for this part of the codebase
- In frontend development, it could be design system, pages, routing, accessibility, state management etc...
- A tech lead or an owner whom has deep expertise in such directory should be overseeing all the changes

3. On a language level

- The code is written in a manner that follows language's style and best practices
- In frontend development, this could be largely automated with tools like Eslintc, Prettier, and TypeScript

It sounds very cumbersome to have an approveal from all three levels of reviews, and to be frank, it sometimes is. In reality, it will often takes one person to assume all three roles because the author would be able to ssume the latter two roles once they have been sufficiently knowledge within the system and language. A code review is then merely requiring a "looks good to me" signature on code correctness and general validity from a reviewer.

I have not encounter any code review that requires more than one approvals in my short professional career, but I foresee this might be common among large scale systems that requires stewardship towards sub atomic systems.

I hope above clarify the underlying reason for code review. Now, lets explores the advantages...

### Code Review Benefits

Many companies and open source projects have code review as one of mechanism to review a change in the codebase. Once you have experienced it, the benefits of this practice is rather obvious, though, it have a cost and effect on engineering velocity(time-to-production) since its introduced additional complexity for the introduction of new code into a codebase.

A well ochatrasted code review process and a culture that embrace it should provide these benefits:

- Coreectness- validity of the code
- Readablity- comprehened by peers
- Consistency- enforcing certain code style
- Ownership- reliability among team
- knowledge Sharing- mutual exchange of information
- A record of change- documentation this timestamp

### Best Practices

Code review is ineffitably a process that creates fraction and drag to merging new code. In order to make it scale with enjoyable experience we should froster a culture of keeping this process smooth and nimble.

- Be polite and professional
- Write small changes
- Include clean and easy to read change descriptions
- Keep reviewer to a minium
- Automate related toolchains

<!-- - outline structure
- write sub-headings
- Add images
- Bulleted list
- bold and italic
- code snippets
- deeper level of sub-headings -->

### Conclusion

<!--
- Short recap
- My opinion and experience
- Ask about their opinion
 -->

Code review is a critical piece of process that acts as a form of open communication with peers. In my experience, I would prefer environment where code review is an essential part of the development process. I feel like there's alot to observe and learn from your peer's coding styles and approaches to solve a problem. At times, I can submit reviews to catch early bugs. It implicitly synchonize the team's code quality, including small changes, fast feedback loop, hence maintain developer's satisfaction and production velocity.

That's it! Hopefully, you've learn something new about code review!

## Reference resources

- [Software Engineering at Google](https://learning.oreilly.com/library/view/software-engineering-at/9781492082781/)

---

If you'd like to see a completed example, the entire source code for my website is [open source](https://github.com/wtLau).

Feel free to [send me a Tweet](https://twitter.com/brian_wtLau) if you have any questions or if I've missed anything.
