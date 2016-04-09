---
layout: post
title:  "Directory Structure In Rails"
tags: directory structure rails ruby
keywords: directory structure rails ruby
description: Explaining the directory structure in Rails application
published: true
---

   TAGS:
   
   {% for tag in page.tags %} {{ tag }} {% endfor %}

  The root directory of `rails` application has a number of auto-generated files and folders that make up the structure of a `Rails` application.
<table border='2'>
  <tr style="color:red;">
<td>File/</td><td>Folder Purpose</td>
</tr>
  <tr>
    <td>app/</td>
    <td>Contains the controllers, models, views, helpers, mailers and assets for your application.
    </td>
  </tr>
  <tr>
  <td>bin/</td>
  <td>Contains the rails script that starts your app and can contain other scripts you use to setup, deploy or run your application.
  </td>
  </tr>
  <tr>
<td>config/</td>
<td>Configure your application's routes, database, and more. 
</td>
</tr>
<tr>
<td>config.ru</td>
<td>Rack configuration for Rack based servers used to start the application.</td>
</tr>
<tr>
<td>db/</td>
 <td>Contains your current database schema, as well as the database migrations.
 </td>
</tr>
<tr>
<td>Gemfile,Gemfile.lock</td>
<td>These files allow you to specify what gem dependencies are needed for your Rails application. These files are used by the Bundler gem.</td>
</tr>
<tr>
  <td>lib/</td><td>Extended modules for your application.</td>
</tr>
<tr>
  <td>log/</td><td>Application log files.</td>
</tr>
<tr>
<td>public/</td><td>The only folder seen by the world as-is. Contains static files and compiled assets.</td>
</tr>
<tr>
  <td>Rakefile</td><td>This file locates and loads tasks that can be run from the command line. The task definitions are defined throughout the components of Rails. Rather than changing Rakefile, you should add your own tasks by adding files to the lib/tasks directory of your application.</td>
</tr>
<tr>
  <td>README.rdoc</td>
  <td>This is a brief instruction manual for your application. You should edit this file to tell others what your application does, how to set it up, and so on.</td>
</tr>
<tr>
<td>Unit tests, fixtures, and other test apparatus.</td>
<td>Testing Rails Applications.</td>
</tr>
<tr>
<td>tmp/</td><td>Temporary files (like cache, pid, and session files).</td>
</tr>
<tr>
<td>vendor/</td><td>A place for all third-party code. In a typical Rails application this includes vendored gems.</td>
</tr>
</table>