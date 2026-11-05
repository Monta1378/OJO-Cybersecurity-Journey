
# Challenge 001: Web Application Security

## Overview

This challenge explored fundamental web application security concepts using a PHP and MySQL invoice application as a case study.

The objective was to understand common web application threats, identify potential weaknesses, and learn appropriate defensive security practices.

## Learning Objectives

- Understand threat modelling and attack surfaces.
- Identify brute-force attack risks.
- Understand SQL injection and prepared statements.
- Distinguish authentication from authorization.
- Understand session hijacking and session security.
- Explain HttpOnly, Secure, and SameSite cookie attributes.
- Understand the relationship between XSS and authenticated browser sessions.

## Threats Studied

1. Brute-force attacks against login forms.
2. SQL injection through insecure database queries.
3. Broken access control on protected pages.
4. Session hijacking and session management weaknesses.
5. Cross-site scripting (XSS).

## Defensive Measures Studied

- Login rate limiting and progressive delays.
- Prepared SQL statements.
- Server-side authentication and authorization checks.
- HTTPS and secure cookie attributes.
- Session ID regeneration and expiration.
- Output encoding and XSS prevention.

## Important Scope Note

This was a learning and threat-modelling exercise.

The application was used as a case study. This repository documents concepts, identified risks, and recommended defensive measures. It does not claim that a complete security audit was performed or that all recommended controls were implemented and tested.

## Supporting Documentation

- [Threat Model](threat-model.md)
- [Security Checklist](security-checklist.md)

## Published Learning Reflection

- [DEV.to article](https://dev.to/jesse_ochoi/what-i-learned-about-web-application-security-threat-modelling-a-php-invoice-application-17d3)
- [LinkedIn reflection](https://www.linkedin.com/posts/jesse-ochoi_cybersecurity-webdevelopment-php-share-7524236938154037248-_bkR/)

## Outcome

This challenge strengthened my understanding of web application security and the importance of considering security during software development.
