# Bookstore

Bookstore is a demo application for Rhetos development platform.

## Build

To build the package from source, run `.\Build.ps1` in PowerShell console.

* If the build fails, see the error description to setup any missing prerequisites.
* If the build fails with an ConnectionString error, follow the instructions in "**Database setup**" chapter at the [Development Environment Setup](https://github.com/Rhetos/Rhetos/wiki/Development-Environment-Setup).

The build output is a web application in `dist\BookstoreRhetosServer` subfolder.

See `docs\Build process diagram.vsdx` for overview of build & testing.

## Testing

Automated tests are executed by running `.\Test.ps1` in PowerShell console.

There are two kinds of tests in this project:

1. **Standard unit tests** (`test\Bookstore.Algorithms.Test`, part of `Bookstore.sln`) that test the algorithm implemented in external assembly.
    * These tests are very fast and independent of the deployment environment.
2. **Integration tests** (`test\Bookstore.ServerDom.Test\Bookstore.ServerDom.Test.sln`) that test the generated applications together with the database.
    * These tests can test full business processes, including the business logic that is implemented in the database, but are slower and need a database to run (the database connection is set up earlier during the Build).

## Web application setup

To setup the IIS web application (`dist\BookstoreRhetosServer` folder) follow the instructions in "**IIS setup**" chapter at [Development Environment Setup](https://github.com/Rhetos/Rhetos/wiki/Development-Environment-Setup).
