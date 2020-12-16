## Generate a lazy-route component
```
ng g m {component name} -route {route name} --module app ((parent module name))
es: 
ng g m about -route about --module app
```

#bundle preloading

install ngx quicklink
npm i ngx-quicklink --save

from 'ngx-quicklink'
import QuicklinkModule in app.module
import QuicklinkStrategy as preloading strategy in RouterModule 

## source-map-explorer:
per trovare dipendenze pensanti

angular.json
outputHashing:true
sourceMap:true
source-map-explorer dist/nomeapp/mainq908eqw09e8qw.js

per risolvere puoi fare ng module con dentro lazy loading

## update angular
ng update @angular/cli @angular/core
update.angular.io

## deploy
ng add @angular/fire
authenticate to firebase
```
ng deploy
```

## other commands
`npm i -f` to force