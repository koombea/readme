## Git Branching and Release Strategy

The repository setup that we use and that works well with this branching model, is that with a central “truth” repo. We will refer to this repo as origin, since this name is familiar to all Git users.

<img src="images/centr-decentr@2x.png" width="487">

Each developer pulls and pushes to origin. But besides the centralized push-pull relationships, each developer may also pull changes from other peers to form sub teams. For example, this might be useful to work together with two or more developers on a big new feature, before pushing the work in progress to origin prematurely.

### Main branches

The central repo holds two main branches with an infinite lifetime:

- master
- develop

The master branch at origin should be familiar to every Git user. Parallel to the master branch, another branch exists called develop.
We consider origin/master to be the main branch where the source code of HEAD always reflects a production-ready state.

We consider `origin/develop` to be the main branch where the source code of HEAD always reflects a state with the latest delivered development changes for the next release. Some would call this the “integration branch”. 

When the source code in the develop branch reaches a stable point and is ready to be released, all of the changes should be merged back into master somehow and then tagged with a release number.

Therefore, each time when changes are merged back into master, this is a new production release by definition.

### Supporting branches

The different types of branches we may use are:

- Feature branches
- Release branches
- Hotfix branches

Each of these branches have a specific purpose and are bound to strict rules as to which branches may be their originating branch and which branches must be their merge targets.

#### Feature branches

May branch off from: develop
Must merge back into: develop
Branch naming convention: `feature/<card_number>-*`

Feature branches (or sometimes called topic branches) are used to develop new features for the upcoming or a distant future release. The essence of a feature branch is that it exists as long as the feature is in development, but will eventually be merged back into develop through a pull request.

Finished features may be merged into the develop branch after the Pull request is approved. 

<img src="images/merge-without-ff@2x.png" width="478">

#### Release branches (Only for UAT environments)

May branch off from: develop
Must merge back into: develop and master
Branch naming convention: `release/<version>`

Release branches support preparation of a new production release. They allow for minor bug fixes and preparing meta-data for a release (version number, build dates, etc.). By doing all of this work on a release branch, the develop branch is cleared to receive features for the next big release.

The key moment to branch off a new release branch from develop is when…

When the state of the release branch is ready to become a real release, some actions need to be carried out. First, the release branch is merged into develop. Next, you need to create a pull request from develop to master. Finally, after the pull request is merged into master, that commit on master must be tagged for easy future reference to this historical version.

#### Hotfix branches

To master:

May branch off from: master
Must merge back into: develop and master
Branch naming convention: `hotfix/*`

They arise from the necessity to act immediately upon an undesired state of a live production version. When a critical bug in a production version must be resolved immediately, a hotfix branch may be branched off from the corresponding tag on the master branch that marks the production version.

<img src="images/hotfix-branches@2x.png" width="316">

When finished, the bugfix needs to be merged back into master, but also needs to be merged back into develop, in order to safeguard that the bugfix is included in the next release as well. In order to merge the changes into master and develop you have to create 2 pull request, one for master and the other one to develop.

To develop:

May branch off from: develop
Must merge back into: develop
Branch naming convention: `fix/<card_number>-*`
