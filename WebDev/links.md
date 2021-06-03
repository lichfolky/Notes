- don't use **click here** links
- “mailto:hello@a11y-collective.com”, “tel:+31108429259"
  it’s better to show the email address or telephone number.
- A link is a promise, not a surprise.
- file type and dimension in file download:
- es: "Web Accessibility Principles (PDF, 327 Kb)". all text linked
- alt test of image better :“Wikipedia page on cherry blossoms” than “A cherry tree in full bloom”.
- Using only a different colour may be problematic for visitors who are colour-blind or visually impaired.
- Underlining is the universal pattern for a link. Users get it right away. So use this pattern for links in paragraphs of text.
  Links that are obviously links, such in navigation menus or buttons, don’t have to be underlined.
- border on focus

<a href="link-to-twitter">
<span class="fab fa-twitter"></span> Twitter
</a>

<a href="link-to-twitter">
<img src="twitter-image.svg" alt="Twitter">
</a>

<a href="link-to-twitter" aria-label="Twitter">
<span class="fab fa-twitter"></span>
</a>

All of these options will thus be announced as “Link Twitter”.

- Internal links
  Link : <a href="#address">Our address</a>
  Destination: <h2 id="address">Address</h2>
  Note: Not only the visual but the keyboard focus should move to the destination. Modern browsers do this by default. Older browsers need a tabindex= “-1” on the destination element to receive the focus. The best way to check this is to test it with an actual keyboard.
