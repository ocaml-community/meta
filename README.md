Note that this README (the manifesto) is a work in progress and is meant to be
collaboratively improved. Please contribute!*

## What is OCaml-community?

OCaml-community is a GitHub organization dedicated to the
collaborative and community-driven long-term maintenance of OCaml
packages.

In other words, the organization provides a place to host open source
OCaml packages that benefit from collective maintenance.

Unmaintained packages that are of significant interest can be adopted
by ocaml-community. Maintenance will then be performed collaboratively
by the community. An official maintainer will be assigned to
individual packages to make decisions about pull requests where
possible.

At minimum, maintenance consists of updating software to keep it
working over time, as well as maintaining the corresponding OPAM
package. It also includes adding needed features, refactoring code,
adding and improving documentation, improving the style of the code,
adding tests, _etc_.

Changes made during maintenance should take into account the needs of
the existing user community, including the need for backward compatibility.

## Who runs this GitHub organization?

This organization is run by
[volunteers](https://github.com/orgs/ocaml-community/people) from the OCaml
community. Everyone is welcome (you don't need to be a very
experienced OCaml programmer to participate).

## How do I submit a package for inclusion?

We currently follow (roughly) the following process:

1. Someone who wants to get a new package included submits an issue to
   the `meta` repository. The issue must contain:
   1. The name of and information about the package, including why it's
      of significance. (This is meant to be a low bar; even a few
      actual users beyond the author is enough to mean "significant.")
   2. The license that the code is under, to allow us to verify it is
      under a reasonable open source license and thus eligible
      for inclusion.
   3. The current location of the most up to date version of the code
      (say a github repository, or an old sourceforge download, or even
      some abandoned tar file on an ftp site.)
   4. Who the last known maintainer was, and what efforts have been
      made to contact them. (Note that the submitter might themselves
      be the last known maintainer.)
   5. If the last known maintainer has been successfully contacted,
      have they agreed to hand over the code? If they disagreed, why do
      you think the code should be adopted anyway?
   6. Have you found someone to act as the initial owner for the code,
      and if so, who will that be? (Typically that will be at least the
      person proposing inclusion, though there may be exceptions.)
2. Following acceptance, the new repository is migrated or
   created. The existing code should be imported _before_ any changes
   are made, to preserve the pre-import state in the version control history.
   1. In the case of a github repository that is being voluntarily handed
      over by the existing maintainer, arrangements should be made to
      transfer the existing repository to the `ocaml-community`
      organization. This will preserve things like existing issues and
      pull requests.
   2. In the case of a repository that was not maintained on GitHub, the
      best known version of the git repository will be imported.
   3. In case of a non-git VCS repository, the repository should be
      converted to git to preserve history and imported.
   4. If the best known version of the code is simply a release
       somewhere (like a tar file), it should be turned into a git
       repository and imported.
3. If the new maintainers are not already part of the
   `ocaml-community` organization, they will be added as collaborators
   on that repository with commit privileges.
4. A few changes should be made to the code as soon as possible
   following repository migration, not necessarily in this order:
   1. A `.travis.yml` file should be added to the repository and the CI
      system should be turned on by an administrator. Generally, builds
      should be tried on the latest several versions of OCaml, on both
      Linux and on MacOS.
   2. The new code owners should be placed into a
      [CODEOWNERS file](https://help.github.com/articles/about-codeowners/)
      in the repository.
   3. The repository should be carefully checked for references to
      old repository locations, home pages, maintainers, etc., and
      these references should be updated.
   4. The code should be updated so that it compiles and runs on the latest
      version of OCaml.
   5. An OPAM package should be created and submitted for the package if
      one does not yet exist, or the existing package should be updated
      to point to the new repository location.
   6. If feasible, older build systems should be converted to `dune`.
5. Following import, the people listed in `CODEOWNERS` are expected to
   handle pull requests and submitted issues with reasonable speed,
   and are expected to keep the package compiling as new versions of
   OCaml are released. If a maintainer cannot continue such duties, or
   requires assistance, they should ask by filing an issue on the
  `meta` repository.

## FAQ

- **Why the name ocaml-community?**

  The ocaml-community organization takes its inspiration from the
  similarly-named [elm-community](https://github.com/elm-community) and
  [coq-community](https://github.com/coq-community) projects.

- **What is the difference between this and the ocaml organization's repositories?**

  The official [ocaml organization](https://github.com/ocaml) is for
  maintaining the [OCaml compiler](https://github.com/ocaml/ocaml) itself,
  [OPAM](https://github.com/ocaml/opam), [odoc](https://github.com/ocaml/odoc),
  and other key infrastructural software. The ocaml-community GitHub
  organization is for adopting and maintaining packages that are of
  widespread use but might lack active maintainers.

- **Can I propose `ocaml-community` adopt a project I wrote?**

  Yes, you can propose a project you wrote, as a way of
  preparing to pass on the maintenance to other community members.

- **How can I propose changes to a package, or to community documentation like this very file?**

  Simply make a pull request. You can also open an issue requesting
  commit access.

- **Will all projects in ocaml-community have some Continuous Integration (CI) set up?**

  CI and automated testing is important for keeping code well
  maintained. We currently make use of the
  [Travis CI](https://travis-ci.org/) system, and we suggest that all
  repositories added to `ocaml-community` should have Travis configs
  added.

## Polite behavior, and what to do if someone else isn't polite.

Contributors to our repositories are expected to behave in a
friendly and welcoming manner. When people contribute fixes to a
project you're helping to maintain, remember that they're spending
time and effort improving open source software, often with no
compensation other than the thanks and good-will of other people. Be
nice, and thank them for the work they've done.

If you don't like some technical aspect of a proposal or
contribution, then try to convey that in a polite and friendly
manner. We're all trying to make the best possible technical
decisions to improve software used by the OCaml community, and being
rude to others interferes with making clear decisions, alienates
valuable contributors, and makes everyone's life more stressful.

If, say, someone is angry and irate when they post a bug report,
there is no reason to reply in a like manner — de-escalate the
situation, don't throw fuel on the fire. (Everyone has bad days, and
there's no reason to turn someone else's bad mood into a sustained
argument.)

It is especially important to never make a technical discussion
personal. Don't make personal attacks against other people, and in
fact, avoid discussing other people when you should be discussing
technical issues. When posting in the issue and pull request
trackers, stick to discussion of the technical merits of a request,
and be polite while you're doing it. Don't stray away from technical
topics.

If the other person isn't being polite, don't respond in kind, it
only escalates things. _At most_, very, very, gently point them at
this text. If the other person's bad behavior is difficult to
ignore, or is habitual, or they have become a problem for the
community, ask the owners of the OCaml-community organization to
intervene. (We will not disclose that you have complained without
your permission.)

(None of this should need saying, as you should probably try to be
polite throughout your life regardless of the situation. Being nice,
even when you're under stress or the other person isn't being nice,
is always the best policy.)
