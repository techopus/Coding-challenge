# pics-app

Task:

[coding-challenge.pdf](https://github.com/techopus/Coding-challenge/files/8693218/coding-challenge.pdf)

- The component fetches the data from the API upon mounting and iterates through the return value creating and image object for each individual images     using the image interface created
- Once all the images are created they are assigned to the images array in the state object.

- In the template, we iterate through the images from the state creating individual divs for each image. Inside each div is a further div for containing the image tags that have the image sources. The author names are displayed below this div.

- The styling is done using grid, and media query for different display sizes. 

## Go to the project directory and run following commands:

1. npm install

2. npm run serve

Result example screenshots:

Desktop -

![desktop-out](https://user-images.githubusercontent.com/92953798/168436206-b0153cc5-07a9-4e24-855f-d070cde1e089.jpg)

Mobile - 

![mobile-out](https://user-images.githubusercontent.com/92953798/168436312-91096014-e838-45e1-b858-977dfb60eb4e.jpg)





## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
