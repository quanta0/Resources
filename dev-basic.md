# Development Basics

## Agenda
* Tools
* Organizing projects

## Organizing Tools
##### Primary Tools
* Sublime Text Editor
* Terminal
* Browser & Extensions

##### Secondary Tools
* Database tools
* Slack

### Sublime Text Editor
#### Advantages
* It is easy to install and use
* Lots of packages to help in development
* File searching is superfast

#### Commands
* ctrl + KB - Toggle your sidebar
* ctrl + N - New File
* ctrl + P - goto anyway. Search files by name in your project
* ctrl + p + @ - Search file as well as method
* ctrl + D - select word (repeat select others occurrences in context for multiple
editing)
* ctrl + / - comment code
* ctrl + shift + / - uncomment code
* Alt + Shift + 1/2/3/4 - Split window into vertical columns
* ctrl + g - used to go to specific line number.

#### Plugins
* Git
* DetectSyntax
* BracketHighlighter
* GitGutter
* sublime-rails-snippets
* coffee script
* SublimeERB
* cucumber

Reference: [http://wbond.net/sublime_packages/package_control
](http://wbond.net/sublime_packages/package_control
)

### Browser
#### AddOns
* colorpicker [chrome]
* yslow
* Responsive Tester [chrome]
* Screen Capture [chrome]
* What Font
* Autofill
* Firebug [mozilla]
* Developer Tool [chrome]
* Ripple [chrome]
* Chrome Remote Desktop
* TMZNS
* railspanel

### Synapse
 Quickly search the required software

## Organizing Projects
* Current Project & references
> Load current project from {project_name}.sublime_project

* Reference Projects
> Load reference projects from references.sublime_project
> Reference Projects
>> *  Diaspora
>> *  Redmine
>> *  FatFreeCRM
>> *  teambox (For specific modules)
>> * Gitlab
>> * Hospitium

* Terminals
> * Log Terminal
> * Rails Console Terminal

## Reference Sites
* [http://www.gotapi.com](http://www.gotapi.com)
* [http://overapi.com](http://overapi.com)
* [https://github.com/bbatsov/ruby-style-guide](https://github.com/bbatsov/ruby-style-guide)
* [https://github.com/bbatsov/rails-style-guide](https://github.com/bbatsov/rails-style-guide)
* [http://guides.rubyonrails.com](http://guides.rubyonrails.com)
* [http://railscasts.com](http://railscasts.com)
* [http://stackoverflow.com](http://stackoverflow.com)
* [http://github.com](http://github.com)
* [http://rubytoolbox.com](http://rubytoolbox.com)
* [http://jquery.com](http://jquery.com)

## Google Search
Reference: [http://www.googleguide.com/advanced_operators.html](http://www.googleguide.com/advanced_operators.html
)

## Issue logging and update format

##### Title
* Should contain path of the module
> Eg: client/edit pagination not working
* Title should describe the exact issue

##### Description
* Explain in detail project issue
* If required explain the issue with some example
* Provide screen shots to understand the issue correctly

##### Issue Update Format
* Explain in detail the solution implemented to resolve issue
* Mention the files modified
* Specify the list of reference links followed to resolve the issue
* Commit : Need to commit frequently while working on issue

### Commit Message Standards
* [[module_name]] [issue_type] [issue_id] message
> Eg: [coupons_controller] Fixed #431 issue of coupon not getting
sorted in correct order

### Gitlab Standards
* Issue should be linked using #<issue_id> Eg: #321
* Merge request should be linked using !<merge_id> Eg: !321
* Snippets are referred using $<snippet_id> Eg: $321
* Users are referred using @user Eg: @admin
* Commit are referred using commit_id

### Developer's Best Practices
* Pull from repository every morning before starting any work, in order keep the branch updated and avoid the conflicts while merging the branch.
* If required merge the latest changes from master into your working branch
* List down checklist for the list of activities to be done
* Should update the daily scrum on Redmine every morning
* Update in Hipchat/Hall after every 30mins on current working task
*Always mention issue with URL while upating message in Hipchat, Hall Redmine, Basecamp
* keep upgrading your knowledge by spending 30 minutes everyday by going through techbox, blogs, twitter etc
* Should log each issue or activity on Redmine & Gitlab, before start working on it.
* Log or update any issue working on frequently
* Should update the list of activities to be performed on the day, on the board.

### Release Note
* Should be prepared for each release, providing as much detail as required.
* Such as branch_name, Explanation about the changes made for the features to be released.
* Effected Modules

### Minutes of meeting
* Needs to be logged after every client call on Redmine.
* Also update the minutes of meeting to Client on Basecamphq (if using) or whatever service used for client updates.

### Branching
* The basic workflow to be followed while on a Project is to create separate branches for separate releases. Default branch would be the master branch.
  All the branches would be created from this branch. We need to maintain different branches to be released at different stages. 

* For development/testing release we should create a development branch, for staging release done for client feedback, we need to create a staging branch
  and Production release will always happen from the master branch. Only the approved and tested code is finally merged to master, which can be   
  released  on the live server.

* We need to checkout the development and staging branches from master
```git checkout -b development
git checkout -b staging```

* So in general there would be three main branches.  New features are developed in the feature branch, fetaure branch is nothing but the branch checked 
  out from master and has the following naming convention, initials of the developer + feature name.
  ```eg: rn_profile_management```

* There would be multiple feature branches.


### Merging
* Once a fetaure is complete, it needs to be released for QA testing, for that feature branch needs to be merged to development branch first. Merging will  
   be done by the senior member of the tem after code review.

* To merge branches, a merge request should be sent to the concerned person of the project

* To create a merge request, go to the your project on gitlab > create a new merge request > select the branch to be merged > select the branch to  
   which it would be merged to > select the assignee > fill in the title and description > select the milestone
   ``` http://code.icicletech.com/path_to_project/merge_requests/new```

* If a merge request is created to merge feature branch 1 to development, and once the merge was successful, the branch needs to be pushed to gitlab,  
  this will close the merge request.

* Once the feature is approved by QA, the next step is to release it on staging server, so the feature needs to be merged to staging branch and there 
  needs to be another merge request for the same.

* After the QA and Client confirms the functionality on staging, the feature can be moved to Production, for which it needs to be merged to master branch 
  and a merge request should be issued for the same.

* Once the feature is merged to master, it can be moved to Production and feature branch can be closed(deleted)

### Tagging and Releases
* Another important aspect that is need to be followed for a release is tag. When the code is finalized to be released, we can create tag, and release the tag 
  on the server. You can also create a branch from a tag, if you want to continue from a particular point of your master branch and do not want to include 
  the code after the second last release, you can checkout the branch from the tag released second last.  
* Format for tag is as follows 

  **Development and Staging Tag**

     ```git tag -a 1.20140226.1 -m "My first commit release"```

  **Production Tag**

     ```git tag -a 1.20140226.1.RC -m "My first commit production release"```

* 1 represents the version of the project, 20140226 is the YYYYMMDD(current date) and .1 represent the number of the tag, i.e 1 states its the first tag 
   for 26th Feb, RC represents the request change and is always applied to Production tag to identify it from staging and development tags 

* You can pass the release notes as the Tag message, create the tag without the message, followed by which you will get the editor 
   opened to paste your entire details of the release. 
   ```git tag -a 1.20140226.1```

* After the release tag is created you need to push the tag to the server.
  To push to heroku, you need to create a remote pointing to your heroku app and push the tag
   
  **Development and Staging Relase**    
     ``` git remote add n4l-dev git@heroku.infra:n4l-dev.git```
     ``` git push n4l-dev 1.20140226.1^{}:master ```


  **Production Release**

     ``` git push n4l-prod 1.20140226.1.RC^{}:master ```



   ***To deploy using Capistrano***
      **Staging Release**
  
       ``` cap staging deploy```

  
   **Production Release**

     ``` cap production deploy ```