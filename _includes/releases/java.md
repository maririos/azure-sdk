{% include releases/header.md %}

## Java

{% if include.type == "all" %}
  {% assign packages = site.data.releases.latest.java-packages %}
{% else %}
  {% assign packages = site.data.releases.latest.java-packages | where: 'Type', include.type | where: 'New', 'true' %}
{% endif %}

{{ description | replace: 'PackageCount', packages.size }}

{% include releases/tabs.md lang="java" active=include.type %}

{% include releases/variables/java.md %}

{% include releases/pkgtable.md %}