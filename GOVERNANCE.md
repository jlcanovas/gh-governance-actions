# Project Governance

The development and community management of the project will follow the governance rules described in this document.

> **NOTE:** Sections and articles in this file are structured to automatize the governance of the project. Please, do not modify the structure of this file.

## 1. Roles

This project includes the following roles.

2.1. **Maintainer**. Maintainers are responsible for organizing activities around developing, maintaining, and updating the Project. Project maintainers will review and merge pull requests.

2.2. **Collaborator**. Any member willing to participate in the development of the project will be considered as a **collaborator**. 

2.3. **Contributor**. Contributors are those collaborators who propose changes to the project's source code. The mechanism to propose such a change is a GitHub pull request.

```governance
rule.roles: ["maintainer", "collaborator", "contributor"]
```

## 2. Project Maintainers

2.1. The team of project maintainers is the following:

 * [Javier Canovas](https://github.com/jlcanovas/) 

```governance
rule.maintainers: [
    { name: "Javier Canovas", github: "jlcanovas"}
]
```

## 3. Issue governance

3.1. Both collaborators and project maintainers may propose issues. The participation in the issue discussion is open and must follow the [Code of Conduct](CODE_OF_CONDUCT.md).

3.2. The group of project maintainers will be responsible for assigning labels to issues, as well as assign the issue to a project maintainer or contributor.

3.3. The group of project maintainers commit to give an answer to any issue in a period of time of 48 hours. 

```governance
rule.issue: {
    who: ["maintainer, "collaborator"],
    deadline: "48 hours",
    labeling: ["maintainer"],
    assignee: ["maintainer"]
}
```

## 3. Pull Request governance

3.1. Both collaborators and project maintainers may propose pull requests. When a collaborator proposes a pull request, is considered contributor.

3.2. Pull requests should comply with the template provided. The assignment of labels and assignees to the pull request is the responsibility of the project maintainers.

3.3. The group of project maintainers commit to give an answer to any pull request in a period of time of 48 hours. 

3.4. The decision of accepting (or rejecting) a pull request will be taken by the group of project maintainers. The decision will be based on the following criteria:

* Two project maintainers must approve a pull request before the pull request can be merged. 
* One project maintainer approval is enough if the pull request has been open for more than 14 days.
* Approving a pull request indicates that the contributor accepts
responsibility for the change. 
* If a project maintainer opposes a pull request, the pull request cannot be merged (i.e., _veto_ behavior). Often, discussions or further changes result in collaborators removing their opposition.

```governance
rule.pr: {
    who: ["maintainer, "collaborator", "contributor"],
    deadline: "48 hours",
    labeling: ["maintainer"],
    assignee: ["maintainer"],
    decision: {
        who: ["maintainer"],
        approval: {
            min: 2,
            minDays: 14
        },
        expired: {
            min: 1
        }
        veto: {
            who: ["maintainer"]
        }
    }
}
```