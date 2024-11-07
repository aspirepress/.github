# Welcome to AspirePress

AspirePress exists to promote the WordPress ecosystem, and to build WordPress into what we all aspire it to be.

## A vision for AspirePress and a community-run .org mirror

### The problem

In the last few weeks, we’ve seen that every WordPress instance in the world has a single point of failure. That single point of failure creates a risk for security, reliability, and credibility for the entire ecosystem. Further, that single point of failure could be leveraged to distribute malware or damage the community as a whole.

This post is about laying out a vision for the future of WordPress, the future of distributing plugin and theme updates, and how we can improve the community as a whole.

### The vision

To address this problem, we have to move in two major steps:

First, we have to get out of disaster mode. We need to assuage the fears of the community by providing a reliable, functional solution that they can use in days, not months.

Second, we should offer a truly distributed, federated and comprehensive update solution that benefits everybody in the community. Getting out of disaster mode

The first goal of the project is to offer a viable solution to the centralized control of the .org website. Here is a short punchlist of my goals, and where we are in the process:

| Status      | Description                                                                                                                                   |
|-------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| DONE        | Develop a plugin that can rewrite the api.wordpress.org and download.wordpress.org endpoints to endpoints controlled by a third party mirror. |
| DONE        | Develop a tool for downloading the entire library of plugins.                                                                                 |
| DONE        | Develop a passthru endpoint that redirects unknown requests to .org                                                                           |
| IN PROGRESS | Develop a tool for updating plugins from the .org                                                                                             |
| IN PROGRESS | Negotiate with a CDN provider for the data and bandwidth we’ll need.                                                                          |
| IN PROGRESS | Implement the basic endpoints for updating WordPress.                                                                                         |
| TO DO       | Set up the ability to issue free API keys to protect the endpoints from abuse, while offering free access to the average user.                |
| TO DO       | Develop a tool for downloading the entire library of themes                                                                                   |
| TO DO       | Develop a tool for updating themes from the .org                                                                                              |
| TO DO       | Develop documentation.                                                                                                                        |
| TO DO       | Setup and test infrastructure                                                                                                                 |
| TO DO       | Launch                                                                                                                                        |

This list is a rough cut of the tasks that need to be completed to effectively launch a mirror of the .org site. It will be updated as we make progress, and also be [updated on GitHub](https://github.com/orgs/aspirepress/projects/1).

The thing is that for this to be a true community project, I need your help. I need people to commit to GitHub, write documentation, test and offer their feedback and critiques. This is a full-court press for the community, and it takes a lot of people to make an open source project work.

### Long-term: distributed, federated, funded

The long-term goals of the project are to effectively ensure three key elements of the mirror system:

* Fully Distributed - anyone can set up a mirror and host plugins;
* Federated - you can join a network of mirrors and have access to their plugins (and yours to them)
* Funded - there be an opportunity for commercial benefit for those who host mirrors, as well as providing open source contributions to the community.

What this looks like in full is for discussion and planning of Phase 2 and beyond, but right now we need to focus on getting something on the table that the community has contributed to and supports so that we can move forward.

None of these concepts is particularly ground-breaking. For example, DNS is distributed and federated. A good mirror should work like DNS: publication of a plugin to one mirror should result in propagation of that plugin to other mirrors that support it and wish to make it available.

### I need your help

This project cannot be done by me alone. While I think I have laid a good foundation, I need experts at devops, coding, marketing, social media, documentation and more to come together to help drive this to the finish line.

If you want to contribute, please contact me, file issues on GitHub, or submit pull requests. Your feedback and involvement is more than welcome.
