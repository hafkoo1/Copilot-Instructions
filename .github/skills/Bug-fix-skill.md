## SKILL BugFix

# Purpose

Systematically find and fix bugs in the ASP.NET Core Web API project while keeping the existing architecture and preventing regressions.

# When to use

Unexpected application behavior occurs

API endpoint returns an incorrect result or status code

Exceptions or errors occur

Validation does not work correctly

Database operations fail

Service or controller logic behaves incorrectly

Problems occur with Entity Framework Core or SQL Server

# Context

Project Architecture: ASP.NET Core Web API with Controllers, Services, DTOs and Entities

Technical Stack: ASP.NET Core, Entity Framework Core, SQL Server, Dependency Injection

Data Layer: AppDbContext with Entity Framework Core

Code Locations: Controllers, Services, Models, Entities, Data and Configuration

Configuration: appsettings.json and dependency injection configuration

# Inputs

Issue Description: Reported bug or unexpected behavior

Error Details: Exception message, stack trace or API response

Code Context: Affected files, methods or endpoints

Reproduction Steps: Steps required to reproduce the bug

Expected Behavior: What should happen

Actual Behavior: What currently happens

Recent Changes: Recently modified code or configuration

# Workflow

1. Issue Investigation

Read the affected controller, service, model and entity

Identify the endpoint or method causing the problem

Analyze exceptions and error messages

Check model validation and input values

Check database and Entity Framework operations

2. Root Cause

Trace the execution flow through controller and service

Check incorrect conditions or null values

Check DTO-to-entity mapping

Check database queries and SaveChanges operations

Determine the actual root cause before changing code

3. Solution

Choose the smallest appropriate fix

Keep the existing architecture

Consider edge cases and possible regressions

Do not change unrelated functionality

4. Implementation

Apply the fix to the affected component

Keep database logic inside services

Keep HTTP logic inside controllers

Add validation or error handling when required

Do not expose internal exception details to API clients

5. Verification

Reproduce the original problem

Test the fixed scenario

Test invalid input and failure scenarios

Run existing unit tests

Build the project and check for compilation errors

6. Prevention

Add a unit test for the bug when appropriate

Check similar code for the same problem

Keep validation and error handling consistent

# Rules

1. Change Discipline

Fix only the reported bug

Make minimal changes

Do not rewrite working code

Preserve existing API contracts

Follow the current project structure and coding style

2. Error Handling

Use appropriate HTTP status codes

Handle expected exceptions correctly

Do not expose stack traces or internal database errors

Return clear and useful error responses

3. Validation

Validate incoming DTOs

Check required values and invalid input

Handle null values correctly

Follow existing DataAnnotations and validation patterns

4. Database

Use Entity Framework Core and AppDbContext

Keep database operations inside services

Do not put database queries directly in controllers

Do not modify migrations or database structure unless required by the bug

5. Logging

Use ILogger<T> when logging is necessary

Do not log passwords, tokens or other sensitive information

Do not add unnecessary logging

6. Testing

Add or update xUnit tests for the fixed behavior

Use Moq for mocking services and dependencies

Test both successful and failure scenarios

Ensure existing tests still pass

7. Security

Validate user input

Do not expose sensitive information

Do not introduce SQL injection vulnerabilities

Preserve existing authorization and authentication behavior

# Validations

Build Validation: Project compiles without errors

Bug Reproduction: Original bug no longer occurs

Regression Testing: Existing functionality still works

Validation: Invalid input is handled correctly

Database: EF Core operations work correctly

API Responses: Correct HTTP status codes are returned

Testing: Relevant xUnit tests pass

Code Quality: Changes follow existing project architecture

# Output

Bug Analysis: Short explanation of the problem and root cause

Affected Code: Files and methods that need changes

Implementation: Complete code with the fix

Explanation: Why the fix solves the problem

Verification: Tests and steps used to verify the fix

Prevention: Test or validation added to prevent the bug from returning

Format: Provide a clear structured response with analysis, implementation and verification.
