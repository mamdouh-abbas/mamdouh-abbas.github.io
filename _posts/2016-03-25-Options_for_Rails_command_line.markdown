---
layout: post
title:  "Options for rails command line"
tags:  ruby rails options
keywords: ruby rails options
description: What is Ruby on Rails command line options
published: true
---

 rails -h
Usage:
  rails new APP_PATH [options]

Options:
<table border='2' >
<tr>
	<th> Option
	</th>
	<th> Details
	</th>
<tr>
<td>-r, [--ruby=PATH]</td>
  <td># Path to the Ruby binary of your choice</td>
  </tr>
  <tr><td>-m, [--template=TEMPLATE]</td>
  <td># Path to some application template (can be a filesystem path or URL)</td>
  </tr>
  <tr>
  <td>[--skip-gemfile], [--no-skip-gemfile]</td>
      <td># Don't create a Gemfile</td>
  </tr>
  <tr>
  <td>
  -B, [--skip-bundle], [--no-skip-bundle]
  </td>
  <td>
  # Don't run bundle install
  </td>
  </tr>
  <tr>
  <td>-G, [--skip-git], [--no-skip-git]</td>
  <td># Skip .gitignore file</td>
  </tr>
  <tr>
  <td>[--skip-keeps], [--no-skip-keeps]</td>
      <td># Skip source control .keep files</td>
  </tr>
  <tr>
  <td>-O, [--skip-active-record], [--no-skip-active-record]</td>
  <td># Skip Active Record files</td>
</tr>
<tr>
  <td>-S, [--skip-sprockets], [--no-skip-sprockets]</td>
  <td># Skip Sprockets files</td>
  </tr>
<tr>
  <td>[--skip-spring], [--no-skip-spring]</td>
      <td># Don't install Spring application preloader</td>
      </tr>
<tr>
 <td>-d, [--database=DATABASE]</td>
  <td># Preconfigure for selected database (options: mysql/oracle/postgresql/sqlite3/frontbase/ibm_db/sqlserver/jdbcmysql/jdbcsqlite3/jdbcpostgresql/jdbc)                                 # Default: sqlite3
  </td>
  </tr>
  <tr>
  <td>-j, [--javascript=JAVASCRIPT]</td>
  <td># Preconfigure for selected JavaScript library# Default: jquery</td>
  </tr>
  <tr>
  <td>-J, [--skip-javascript], [--no-skip-javascript]</td>
  <td># Skip JavaScript files</td>
  </tr>
  <tr>
  <td>[--dev], [--no-dev]</td>
      <td># Setup the application with Gemfile pointing to your Rails checkout</td>
  </tr>
  <tr>
  <td>[--edge], [--no-edge]</td>
      <td># Setup the application with Gemfile pointing to Rails repository</td>
  </tr>
  <tr>
  <td>[--skip-turbolinks], [--no-skip-turbolinks]</td>
      <td># Skip turbolinks gem</td>
      </tr>
  <tr>
  <td>-T, [--skip-test-unit], [--no-skip-test-unit]</td>
  <td># Skip Test::Unit files</td>
  </tr>
  <tr>
  <td>[--rc=RC]</td>
      <td># Path to file containing extra configuration options for rails command</td>
  </tr>
  <tr>
  <td>[--no-rc], [--no-no-rc]</td>
      <td># Skip loading of extra configuration options from .railsrc file</td>
  </tr>
  <tr>
  <td colspan="2">Runtime options:</td>
  </tr>
  <tr>
  <td>-f, [--force]</td>
  <td># Overwrite files that already exist
  </td>
  </tr>
  <tr>
  <td>-p, [--pretend], [--no-pretend]
  </td>
  <td># Run but do not make any changes
  </td>
  </tr>
  <tr>
  <td>
  -q, [--quiet], [--no-quiet]</td>
  <td># Suppress status output
  </td>
  </tr>
  <tr>
  <td>-s, [--skip], [--no-skip]</td>
  <td># Skip files that already exist
  </td>
  </tr>
  <tr>
  <td colspan="2">
Rails options:
</td>
  </tr>
  <tr>
<td>-h, [--help], [--no-help]
</td>
<td># Show this help message and quit
  </td>
  </tr>
<tr>
  <td>-v, [--version], [--no-version]</td>
  <td># Show Rails version number and quit</td>
  </tr>
  </table>
  <style type="text/css">
tr>td:first-child {
	color:blue;
}
  </style>