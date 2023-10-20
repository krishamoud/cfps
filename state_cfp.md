# Stateful is the opposite of Stable

## Format
30-40 min talk with Q&A

## Brainstorm
- State is brittle
- State is everywhere
    - Code/Version Control, 
    - Ruby version, gem versions, node versions
    - dependency versions
    - operating systems
    - environment variables
    - Local dev environment
    - data in the database
    - There are only two hard things in Computer Science: cache invalidation and naming things.
- Problems state can cause
    - two different versions of code do different things
    - gem versions can break existing functionality
    - OpenSSL, imagemagick, etc. can change or break existing functionality
    - Debian(glib c) vs Alpine (musl) can change or break existing functionality
    - Different env var values existing at the same time can change or break existing functionality
    - MacOS vs Linux vs Windows vs docker vs nix can cause different expected behaviors in production
    - missing migrations or poor data integrity can lead to unexpected behaviors
- This problem exists beyond just your application code
    - MySQL major version, minor version, operating system, configuration
    - Redis major version, minor version, operating systemm configuration
    - Infrastructure configuration
- Ways we solve for state
    - VCS (git, subversion, mercurial)
    - Gemfiles, Gemfile.lock
    - Docker/Packer
    - Docker/Packer
    - Secret store (e.g. vault)
    - Extensive Documentation, remote dev environment, other?
    - Solid CI/CD pipeline
- State is unavoidable
    - Languages/gems need upgrading
    - Operating systems need upgrading
    - New Env vars need to be set
    - Databases need to store state
    - Only change one at a time for an accurate prognosis of changes

## Audience
Web developers of all levels from all frameworks.  Talk could be tailored based on the community e.g. rails vs python vs node, etc.


## Outcomes/Conclusions
I want the audience to have an understanding of how bugs can sneak into production even after extensive testing.  I want the conclusion to be that maintaining state is unavoidable but reducing it's scope to the smallest surface area possible and only changing the state of one thing at a time is the easiest way to ship software quickly and safely.


## Outline
See ##brainstorm

## Description
Modern web applications can be complicated. As they increase in complexity we must be vigilant about understanding how all the pieces fit together.  It is our job as developers to change the state of the applications we build but we must understand that changing the state of one piece can change how our application works fundamentally.  We must be intentional about what we're changing, why, what the expected outcome is, and how to meassure it's success.

## Abstract
This talk is important because as web applications increase in complexity, the difficulty in debugging them also increases.  This talk could help developers learn how to reduce the surface area of the bugs their code could produce.  The talk will acknowledge that bugs are inevitable but we can make finding them, reproducing them, and fixing them easier.  The talk will achieve that by teaching techniques to reduce state transitions across the entire stack which makes isolating bugs to specific changes easier to detect.  Following these techniques is how ConvertKit scaled from a $13M/year business to a $40M/year business with only two infrastructure engineers.

## Submitted to
- ...


## Given at
- ...

[Format Credit](https://mercedesbernard.com/blog/start-conf-speaking-abstract/)