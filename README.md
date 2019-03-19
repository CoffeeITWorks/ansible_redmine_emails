# Role

[![Build Status](https://travis-ci.org/CoffeeITWorks/ansible_redmine_emails.svg?branch=master)](https://travis-ci.org/CoffeeITWorks/ansible_redmine_emails)

Main purpose is to setup cron tasks for redmine to read emails from imap server.

    redmine_admin_mail: youradmin@yourdomain.com

## Mail that will be set on the from field whend Redmine send notificaitons

    redmine_mail_from: yourmailfrom@yourdomain.com
    redmine_domain: "redmine.yourdomain.com"

    # You could also use a domain set in your inventory file,
    # ex : redmine_domain: "{{ hostvars[groups['redmine_server'][0]]['red_domain'] }}"
    # will use the red_domain property of the first host defined in a group remdine_server

## Setup your emails to receive from: 

    redmine_email_receive:
      enabled: false
      username: emailuser
      password: emailpassword
      default_project: defaultprojecttoassignnew
      server: imap_server
      port: 993
      ssl: SSL
      allow_override: project,tracker,status,priority,category,assigned_to,fixed_version,start_date,due_date,estimated_hours
