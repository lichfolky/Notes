The new responsive

- User based preferences and needs
  prefers-reduced-motion
  prefers-contrast
  prefers-reduced-transparency
  prefers-color-scheme
  prefers-inverted-colors

@media (prefers-reduced-motion: no-preference){
.face{
backface-visibility: hidden;

}

.back{
transform: rotateY(180deg);
opacity:1;
}
.back:focus, .back:hover, .back:focus-within, {
transform: rotateY(180deg);
}
}
@media (prefers-color-scheme: dark){
:root{
new colors vars
primary
on-primary
secondary
surface
on-surface
background
on-background
}
}

check on rendering

dont use saturated color on dark themes because they vribrate visually
do use 200-50 range light colors

use light instead of shadows in a dark theme

container queries

container based responmsive design
based on his parent container
it ask the parent container for info rather than user agent and global viewport

.card{contain: size layout;}
@container(max-width: 850px){
.links{ display:none:}

}

inline sizes and block size values
layout ng grid implementation

chrome://flags >>> enable CSS Container Queries

@scope (.tabs) to (.panel)
:scope{root of the scope}

form factor new screens like foldable screens

web stories dev tools>
add #development=1 at the end of the url

@media screen and (min-width: 600px), screen and (orientation: landscape) {
:is(d) :where()
