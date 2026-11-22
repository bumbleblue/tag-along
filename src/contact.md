---
layout: base.njk
title: Get in touch
permalink: /contact/
description: "Questions about running a Tag along, an event to list, or feedback on the playbook? Write to us."
---

# Get in touch!

Planning a *Tag along* in your city, or running one we should [list](/events/)? Found a gap in the [Playbook](/playbook/)? Write to us.

<form name="contact" method="POST" action="/thanks/" data-netlify="true" netlify-honeypot="bot-field">
  <p class="visually-hidden" aria-hidden="true">
    <label>Don't fill this out if you're human: <input name="bot-field"></label>
  </p>
  <label for="name">Name</label>
  <input type="text" id="name" name="name" autocomplete="name">
  <label for="email">Email <span aria-hidden="true">*</span><span class="visually-hidden">(required)</span></label>
  <input type="email" id="email" name="email" required autocomplete="email">
  <label for="message">Message <span aria-hidden="true">*</span><span class="visually-hidden">(required)</span></label>
  <textarea id="message" name="message" rows="7" required></textarea>
  <button type="submit">Send it over</button>
</form>

For code-of-conduct concerns, please email [{{ site.cocEmail }}](mailto:{{ site.cocEmail }}) directly, as described in our [reporting guidelines](/code-of-conduct/#reporting-guidelines).
