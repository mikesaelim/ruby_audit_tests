# ruby_audit_tests

Temporary(?) repo of automated integration tests for [RubyAudit](https://github.com/civisanalytics/ruby_audit)

RubyAudit is built atop [Bundler-audit](https://github.com/rubysec/bundler-audit), and both are built atop
the [ruby-advisory-db](https://github.com/rubysec/ruby-advisory-db).  So we need some integration tests
running on a schedule to alert us if this integration breaks.

This integration test runs weekly on Fridays, and checks that security advisories for a MRI Ruby version, a JRuby version, and a rubygems version are found.  If it fails, GitHub emails me.

----

Possible TODOs:
* GitHub automatically disables workflows on public repos that haven't had new commits in 60 days, so I have to reenable the workflow every 60 days.  Consider adding a keep-alive step that does this automatically.
* Add more test cases?
* Workflow step that creates a GitHub issue if any actions failed
* Port this over to civisanalytics/ruby_audit?
