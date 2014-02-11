php-test
========

What is this?

This project was created to make easier the procedure of updating production servers with new versions of other projects (generally it was designed for web applications, but there is no limitation of use).

Overall effect is an upgraded git cloning, which gives you the opportunity to merge new changes straight to the testing and production servers with appropriate real configurations, while hiding these configurations from public repositories.

For example, you have some project ‘A’, which is already in production stage and a copy of it with changed production settings is hosted somewhere. All is fine for some time, but then you want to add a new feature or fix some bugs / security issues. With webhook you can make and commit changes to test branch, immediately test it and commit to master branch, which will be automatically synced to production server with saved production settings.
How it works

Synchronization goes in 4 steps:
1. Permission checks (IP filtering)
2. Validation and processing of incoming parameters
3. Forming the list of tasks to synchronize
4. Repository cloning (or pulling if already cached), replacing configuration files and uploading to the server(s)
