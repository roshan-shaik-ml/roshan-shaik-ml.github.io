---
title: Authz vs Authn
date: 2024-12-29 22:40:46 +0530
categories: [vulnerabilities, api_security]
tags: [authz, authn, api, security]     # TAG names should always be lowercase
---

![Authentication vs Authorization](/assets/images/authentication-vs-authorization-difference.webp)
## Basics

How are authn and authz different?

 To put it simply, authn has to do with *identity*, or who someone is, while authz has to do with *permissions*, or what someone is allowed to do.

## What is authentication (authn)?

Authentication means making sure that a person or device is who (or what) they claim to be. A person picking up tickets for an event might be asked to show their ID card to verify their identity; similarly, an application or database may want to make sure that a user is legitimate by checking their [identity](https://www.cloudflare.com/learning/access-management/what-is-identity/). Authentication ensures that data is not exposed to the wrong person.



## What are some common authn methods?

- Username and password combination

- Multi-factor authentication (MFA)

- Public key certificate

- Biometric authentication

## What is authorization (authz)?

Authorization determines what an authenticated user can see and do. Think of what happens when a bank customer logs in to their account online. Because their identity has been authenticated, they can see their own account balance and transaction history — but they are not authorized to see anyone else's. A manager at the bank, conversely, could be authorized to see any customer's financial data.

Similarly, a person may be a legitimate employee of a business, and they may have verified their identity, but that does not mean they should have access to all of that business's files and data. An employee from outside the HR or accounting departments should not be able to see everyone's compensation, for instance.

A user's authorization level determines what they have permission to do; therefore, a common term for authorized actions is "permissions." Another term for this concept is "privileges."

## How does authz work?

In **role-based access control (**[RBAC](https://www.cloudflare.com/learning/access-management/role-based-access-control-rbac/)**)**, every user is assigned one or more predetermined roles, and each role comes with a specified set of permissions.

In **attribute-based access control (ABAC)**, users are assigned permissions based on their attributes or the attributes of the action they are trying to perform.

In **rule-based access control** (also abbreviated as RBAC), actions are allowed or denied based on a set of rules that apply to all users, irrespective of their role.

#### References

[Authn vs. authz: How are they different?](https://www.cloudflare.com/learning/access-management/authn-vs-authz/)

[WTH is OAuth?](https://app.capacities.io/afcfe486-c51c-44b9-a658-b4362ef39aec/1ec683da-9c9e-412d-b007-de9d719057ab)
