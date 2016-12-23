---
layout: page
title: Contact
permalink: /contact/
tags: contact
---

<div class="py2">
  {% if site.ajaxify_contact_form %}
    <form class="form-stacked">
      <input type="text" name="email" class="field-light" placeholder="{{ site.text.contact.email }}">
      <textarea type="text" name="content" class="field-light" rows="5" placeholder="{{ site.text.contact.content }}" style="resize: vertical"></textarea>
      <input type="text" name="_gotcha" style="display:none" />
      <button type='submit' class="button button-blue button-big mobile-block">{{ site.text.contact.submit }}</button>
    </form>
  {% else %}
    <form action="https://formspree.io/{{ site.email }}" method="POST" class="form-stacked">
      <input type="text" name="email" class="field-light" placeholder="{{ site.text.contact.email }}">
      <textarea type="text" name="content" class="field-light" rows="5" placeholder="{{ site.text.contact.content }}" style="resize: vertical"></textarea>
      <input type="hidden" name="_next" value="{{ site.baseurl }}/thanks/" />
      <input type="hidden" name="_subject" value="{{ site.text.contact.subject }}" />
      <input type="text" name="_gotcha" style="display:none" />
      <input type="submit" class="button button-blue button-big mobile-block" value="{{ site.text.contact.submit }}">
    </form>
  {% endif %}
</div>

{% if site.ajaxify_contact_form %}
  {% include ajaxify_content_form.html %}
{% endif %}