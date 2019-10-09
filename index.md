# MOJ Digital Probation Services - Development

This guide documents the coding standards and quality control tools proposed for use
as part of the Digital Probation Services, this builds on top of the guidance
provided in the [MOJ technical guidance](https://ministryofjustice.github.io/technical-guidance) and the [The GDS Way](https://gds-way.cloudapps.digital/)

## Standards

{% assign standards = site.pages
  | where: "standard", true
  | group_by: "category" %}

{% for standard_group in standards %}
### {{ standard_group.name }}

{% for standard in standard_group.items %}
- [{{ standard.title }}]({{ standard.url | relative_url }})
{% endfor %}
{% endfor %}

## Guides

{% assign guides = site.pages
  | where: "guide", true
  | group_by: "category" %}

{% for guide_group in guides %}
### {{ guide_group.name }}

{% for guide in guide_group.items %}
- [{{ guide.title }}]({{ guide.url | relative_url }})
{% endfor %}
{% endfor %}
