---
title: Build Errors
modified_at: 2015-03-24 00:00:00
tags: app error deployment quota
---

When your application is deployed, the dependencies are gathered and are packaged
into an _application image_

## Invalid return code from buildpack

You application image is built using a buildpack ([List of buildpacks]({% post_url platform/deployment/buildpacks/2000-01-01-intro %})).
If the buildpack exits with an error, it is probably linked to your project. You should
be able to see the content of the error in your console. Then adapt your code according to it.

If you think the error comes from our buildpacks, feel free to contact us and we will fix
it as soon as we can.

## Image too large

The maximal size of an application image is __650MB__. If your assets, your
dependencies and the code of your application weigh more than this limit,
different solutions are available to lighten the image of your application:

* Try to remove unused external dependencies or assets.
* Define a [.slugignore file]({% post_url platform/app/2000-01-01-slugignore %}) to exclude files from the
  image.

If you absolutely need all these data, please contact us at
[support@scalingo.com](mailto:support@scalingo.com).

{% note %}
  Why this quota? Besides being a simple security limit, this quota is also present to
  preserve the PaaS user experience. A large image results in longer deployments, the
  instantaneity aspect is lost.
{% endnote %}