# Chef Cookbook DIY Github Action
### Workflow Details
[Chef](https://www.chef.io/) is widely used and most popular Infra as code technology in DevOps World.

This specific GitHub Action Workflow has been used for creating DIY deployment for Chef cookbooks. 
The below mentioned Continuous Integration aspects are covered in the Workflow,
- It checks-out the code into Workspace
- Performs Cookbook Code Analysis using `cookstyle`
- Executes the cookbook in local mode (`chef-client - z` option)
- Executes the `rspec` unit test cases  (Chef cookbook **B**ehaviour **D**riven **D**evelopment)
- Packages the cookbooks using `Berkshelf` which uses `berksfile` 
- Creates tar.gz archive of Cookbook packages
- In case of any workflow failures, it sends out email to respective developers and maintainers of the repository

Here is the link to [Github Action Workflow file](https://github.com/chefgs/dev_github_actions/blob/master/.github/workflows/cookbooks_ci_job.yml)

### Cookbook Details
Cookbook performs below tasks,
- Creates an user group called `chefusers`
- Creates an user called 'bob'
- Creates a directory `cheftest` in '/tmp'
- Creates a file `chef.txt` inside `cheftest` and assigns user 'bob' and group 'chefusers' to the file
