# concourse-svn-resource
SVN access for Concourse CI.

Currently implemented in NodeJS, using the node:5 docker image.

## Resource Configuration

```yaml
resource_types:
- name: svn-resource
  type: docker-image
  source:
    repository: robophred/concourse-svn-resource

resources:
- name: svn-code
  type: pull-request
  source:
    repository: http://your-svn-repository
    username: {{username}}
    password: {{password}}
```

### Source options

* `repository`: The subversion repository to operate on
* `username`: *Optional.* The username to log in as.
* `password`: *Optional.* The password to log in with.
* `trust_server_cert`: *Optional.*: If true, trust invalid server ssl certs.
 
More information on using custom resources can be found at the [concourse documentation](http://concourse.ci/configuring-resource-types.html)

## Current status

*check* and *in* are implemeted, but neither has been tested on concourse as of yet.  Stay tuned for updates.

### check

Initial implementation is completed.  However, it currently returns only the most recent revision.

### in

Initial implementation is completed.

### out

Initial implementation is completed.
