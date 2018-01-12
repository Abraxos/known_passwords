# Known Passwords

A database schema, webapp, and utilities for searching, managing, and checking inclusion in a set of passwords known to hackers

## Introduction

At some point in early 2018, someone dumped a massive set of 1.5 billion username and password combinations online. In response to this, I decided to create this webapp which is intended to allow the following activities:

1) The ability to securely check whether a given password exists in the database and should therefore not be used
2) The ability to add more known/compromised usernames/passwords into the database
3) Search the database for usernames to determine whether one's password has been compromised

The ideal use case for this webapp is to check new account passwords to see if they have already been compromised before the user manages to create an account, and preventing them from doing so with an insecure password.

## Warning

Please be advised that there are multiple security concerns and caveats that need to be addressed before using this webapp:

1) The passwords are hashed using SHA512 before being sent to the database for verification, that way, you're not sending passwords to the webapp server for casual checks. That being said, this should only be done on a secure connection. As a result, this webapp is designed to work ONLY over HTTPS and uses both server and client-side verification. This means that both the server and the client must have valid certificates from some certificate authority.
2) This database can definitely be used for evil. Don't. You've been warned. You will be caught, and you will go to jail. If you think you won't, you will _definitely_ get caught.
3) It should only ever run on your private network exposed only to trusted servers.

## The WebApp

This part is currently under development

## Utilities

**Import** - Designed to import passwords from a directory of files where every line is of the pattern: `username:password`. This utility allows you to import a database dump into the database schema for use by this webapp.