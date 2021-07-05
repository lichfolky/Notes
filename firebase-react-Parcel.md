Here is a gist of what to do if you are deploying your Parcel/React project on firebase. 
1. add these scripts to your package.json in the root of your project 
Package.json:

"scripts": {
    "clear-build-cache": "rm -rf .cache/ dist/",
    "dev": "parcel src/index.html",
    "build": "cross-env NODE_ENV=production parcel build ./src/index.html --public-url ./",
    "format": "prettier --write \"src/**/*.{js,jsx}\"",
    "lint": "eslint \"src/**/*.{js,jsx}\" --quiet",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  
  make sure your index.html path is correct in the build script 
  dev: npm run dev will run your project locally. 
  clear-build-cache: npm run clear-build-cache will clear your .cach and dist file before running your build 
  format: npm run format it will run prettier for all your files.
  
  2. than remove dist and cache files or you can run npm run clear-build-cache like mine in the package.json
  3. now run npm run build. which it will make a dist folder for your project 
  4. init your firebase and make sure that your firebase.json public is connected to dist folder
  
  Firebase.json:
  
  "hosting": {
    "public": "dist/",
    "ignore": [
      "firebase.json",
      "**/.*",
      "**/node_modules/**"
    ],
    "rewrites": [
      {
        "source": "**",
        "destination": "/index.html"
      }
    ]
  }
  
  5. Now it is time to run firebase deploy and deploy your project. 
  Please let me know if this is helpful to anyone. 
  
  