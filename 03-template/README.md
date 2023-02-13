# Ansible Template

- Ansible template module helps to template a file out to a remote server.
- Simply put, at runtime ansible template module updates the jinja2 interpolation syntax variables with actual and copy the template file to the remote server with the specified name.

## Ansible template module

- Ansible template module does to things :
- Replace the jinja2 interpolation syntax variables present in the template file with actual values.
- Copy (scp) the file to the remote server.
- Ansible template module is designed to perform only these two things and it does same perfectly and before going to Ansible template it is necessary that we should understand the Ansible interpolation syntax and how it works.

# Jinja2 ?

- Jinja2 templates are simple template files that store variables that can change from time to time. When playbooks are executed, these variables get replaced by actual values definied in Ansible Playbooks. This way, templating offers an efficient and flexible solution to create or alter configuration file with ease.

# Project

- Install prometheus using Ansible which is a monitoring tool used by most of the organization because its open source tool.

## Steps Involved:

- 1 - Download prometheus binary from Prometheus official website.
- 2 - Copy and Unarchive or unpack the prometheus binary on target system.
- 3 - Create prometheus as a service on the target system.
