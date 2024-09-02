---
layout: workshop
venue: "University at Buffalo, SUNY"   # brief name of host site without address (e.g., "Euphoric State University")
address: "University at Buffalo, SUNY, North Campus, Natural Sciences Complex"   # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "United States"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes)
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)
latitude: "43.002890"     # decimal latitude of workshop venue (use https://www.latlong.net/)
longitude: "-78.788780"    # decimal longitude of the workshop venue (use https://www.latlong.net)
email: ["alexeyak@buffalo.edu"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
carpentry: "sc"
---


{% comment %}
root: .  # Is the only page that doesn't follow the pattern /:path/index.html
permalink: index.html  # Is the only page that doesn't follow the pattern /:path/index.html
{% endcomment %}


# OpenPhysChem resource

## Description

This website will contain useful resources for undergraduate and graduate classes interested in Physical Chemistry

## Logistics

{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% if page.latitude and page.longitude %}
<p id="where">
  <strong>Where:</strong>
  {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latitude}}&mlon={{page.longitude}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latitude}},{{page.longitude}}">Google Maps</a>.
</p>
{% endif %}

{% comment %}
CONTACT EMAIL ADDRESS
Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact</strong>:
  Please email
  {% if page.email %}
  {% for email in page.email %}
  {% if forloop.last and page.email.size > 1 %}
  or
  {% else %}
  {% unless forloop.first %}
  ,
  {% endunless %}
  {% endif %}
  <a href='mailto:{{email}}'>{{email}}</a>
  {% endfor %}
  {% else %}
  to-be-announced
  {% endif %}
  for more information.
</p>


### Acknowledgement

For now, this is a pilot project. I hope to thank NSF in the future. 


{% include links.md %}
