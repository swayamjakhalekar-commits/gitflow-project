# Gitflow Project

A Git repository demonstrating the **Gitflow workflow**, created as a final project for the Version Control with Git course.

## Overview

This project simulates a team building and releasing a product using Gitflow. It covers:

- Feature branch development
- Release branch preparation with bug fixes
- Hotfix branching for critical post-release bugs
- Merging, tagging, and rebasing

The first release (**v1.00**) includes one feature. Shortly after release, a bug was discovered and a hotfix (**v1.01**) was applied.

## Commit Graph

```
* F2 - feature 2 wip (feature2, rebased onto develop after hotfix)
* M  - Merge branch 'hotfix1' into develop
|\
| * K  - fix feature 1 bug Y (hotfix1)
* | L  - Merge branch 'hotfix1' (tag: v1.01)
|/
* I  - Merge branch 'release1' into develop
|\
| * G  - fix feature 1 bug X (release1)
* | H  - Merge branch 'release1' (tag: v1.00)
|/
* E  - Merge branch 'feature1' into develop
|\
| * D  - add feature 1 (feature1)
| * C  - feature 1 wip
|/
* B  - add fileA.txt (develop)
* A  - add README.md (master)
```

## Branches

| Branch | Purpose |
|--------|---------|
| `master` | Production-ready code with tagged releases |
| `develop` | Integration branch for features |
| `feature2` | Ongoing feature development (rebased twice) |

## Tags

| Tag | Description |
|-----|-------------|
| `v1.00` | First release — feature 1 with 1 known bug |
| `v1.01` | Hotfix release — all feature 1 bugs resolved |

## Commit Details

| Commit | Branch | Message | fileA.txt Content |
|--------|--------|---------|-------------------|
| A | master | add README.md | — |
| B | develop | add fileA.txt | *(empty)* |
| C | feature1 | feature 1 wip | `feature 1 wip` |
| D | feature1 | add feature 1 | `feature 1 with 2 bugs` |
| E | develop | Merge branch 'feature1' into develop | *(no change)* |
| F | feature2 | feature 2 wip | `feature 1 with 2 bugs` + `feature 2 wip` |
| G | release1 | fix feature 1 bug X | `feature 1 with 1 bug` |
| H | master | Merge branch 'release1' | `feature 1 with 1 bug` |
| I | develop | Merge branch 'release1' into develop | `feature 1 with 1 bug` |
| F1 | feature2 | feature 2 wip (rebased) | `feature 1 with 1 bug` + `feature 2 wip` |
| K | hotfix1 | fix feature 1 bug Y | `feature 1` |
| L | master | Merge branch 'hotfix1' | `feature 1` |
| M | develop | Merge branch 'hotfix1' into develop | `feature 1` |
| F2 | feature2 | feature 2 wip (rebased) | `feature 1` + `feature 2 wip` |

## How to Verify

Clone the repository and run:

```bash
git log --all --oneline --graph --decorate
```

Check tags:

```bash
git tag -l
```

Check branches:

```bash
git branch -a
```

Check file content on any branch:

```bash
git checkout <branch>
cat fileA.txt
```

## Tools Used

- Git (command line on Windows)
- GitHub (remote repository)

## License

This project was created as a learning exercise based on the Atlassian Version Control with Git course.
