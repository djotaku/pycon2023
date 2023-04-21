# Why You Should Care About Open Source Supply Chain Security

You should definitely care if you use OSS

These attacks can be challenging to detect - specially because projets are usually volunteer run and transitive dependecies can be hard to keep track of. And if it's a binary, you may not understand the dependencies.

## Ways compromises happen

- Unauthorized changes - eg The Linux Hypocrite Commits
- Compromised source repo - eg Compromised PHP self-hosted git server was compromised and backdoors were added to the source code. The commits seemed to come from a real contributer
- Build from modified source - Webmin - an attacked modified the build to use a different source. Back-doored versions were available for over a year. Compromised code was in the package, but not Github since it was pulling from a malicious source
- Compromised Build Process - eg Solar Winds
- Using Compromised Dependencies - eg Attacker offered to take over popular unmaintained project. Updated the dependency with malicious behavior. Hosted package version didn't match source.
- upload modified package - eg CodeCov - attacked userd leaked creds to upload malicious artifact to bucket
- Compromised Package repo - 
- User could end up using a compromised package because of typo squatting
- Dependency becomes unavailable - a maintainer can intentionally remove a package from the repo without warning

## What questions do we need to answer about software?

- Can we verify identify of build runner?
- what source code was it built from?
- What git commit does it map to?
- does the project use security posture I need them to?

[Scorecard](https://github.com/ossf/scorecard/) checks a repo for some security practices

Sigstore - an open source, free to use project. Allows for securely signing software artifacts. It stores the sigs in a public log that can be checked. Key management not needed because of the tech used in this project. 

SLSA - an open source framework to describe what's ni the build, where it was built, etc. Useful for generating a SBOM (Software Build of Materials) 1.0 version just came out the week of this conference (19 April 2023)

SLSA is based on levels.

- Level 0 - No guarantees
- Level 1 - Provenance data
- Level 2 - Signed provenance plus hosted build platform
- Level 3 - Hardened build platform was used to build the code

Risks can come from both direct dependencies and indirect dependencies (which are harder to find)

There are also transitive dependencies.

## What happens when dependencies go missing?

Story about dep that caused React to break when it stopped being provided. Same happened to ruby on rails.

## What's happening?

Governments are starting to make mandates

Many package repos are starting to make changes



