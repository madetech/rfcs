# Slack channel names

## Summary

Guidelines for slack channel naming conventions building on [Slack's own guidelines](https://get.slack.help/hc/en-us/articles/217626408-Create-guidelines-for-channel-names).

## Problem

There is no standard naming convention for Slack channel names and as we grow they become harder to discover. It's difficult to understand whether a channel is for discussion on topics or with teams. For example some SRE questions go into #live-services, some into #help, #engineering and even into #announcements.

## Proposal

- You SHOULD create discussion channels for particular engineering topics such as Kubernetes, React, etc.
- You SHOULD create team channels for all teams within the business whether delivery teams, sales, etc.
- You SHOULD create project channels for particular team projects that have a focussed goal, an example would be Homes HIF is a project of the Homes team.
- You MAY create collaboration channels and invite customers to them if you want to use Slack as a communication tool.

- You MUST prefix engineering topics with `#eng-`. For example, `#eng-k8s`, `#eng-react`, `#eng-tdd`.
- You MUST prefix team channels with `#team-`. For example `#team-dmc`, `#team-sales`, `#team-people`, `#team-homes`, `#team-sre`.
- You MUST prefix project channel with `#proj-`. For example `#proj-dmc-watg`, `#proj-homes-hif`, `#proj-productionisation`.
- You MUST prefix collaboration channels with `#collab-`. For example `#collab-dmc`, `#collab-khc`.
