# AspNet Identity Quickstart

This repository contains a quickstart project that you can easily fork and integrate with your application's for Identity integration.

## SendGrid
I'm using SendGrid to send emails (account activation, password reset, activation resend, etc.). SendGrid has a Free pricing plan that allows you to send up to 100 emails per day, which is sufficient at least for dev to staging levels of your application.

All you need to do after creating the account is generate a new api key and set it on the appsettings.json alongside your SendGrid sending Email.

## Database Support
The project supports MySql out of the box. Just fill the appsettings.json with your MySql server information.

If you want a different engine, just swap it out and regenerate migrations.


## Custom Identity Objets.
The most relevant objects to start with: User Role UseRole are already available as custom objects: ApplicationUser, ApplicationRole, ApplicationUserRole, with the corresponding relationships accessible.

## Jwt Support
After login a query parameter is returned to ReturnUrl like ?token=jwt_token that contains a valid jwt token

## Pre-Existing Roles
This application makes use of other of my Projects: "CoreArk" which contains some base services and Enums that help achieving fast prototypes and even solid applications from the ground up.
One of those packages contains an enum: UserRole with the roles: 

*  User = 0: a common user with basic functionalities, mainly self data reading and inspection.
*  Support = 1: a user that is capable of assiting an administrator, can mainly read and update data
*  Administration = 2: the user with all capabilities that refer to a company (which users belong to)
*  Sysadmin = 4: A BackOffice user that can administer the system and access company data 

You are free to change that in ApplicationDbContext.cs by adding other roles or removing them and re-generating the Initial Migration.

