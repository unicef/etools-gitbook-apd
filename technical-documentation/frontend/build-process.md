# Build process

You can use Gulp comands to build TPM application. There is difference beetwen building module for development or production. Details of realisation specific gulp tasks you can find in `gulp-tasks/` directory.

### Development

Use this command to build application for development:

```text
gulp devup
```

This comand will run several gulp tasks. It will clean destenation directory,  build source files using polytempl, babel and other plugins, copy necessary assets and bower components. Than it will run node server by executing `express.js` file and start watching changes in application source files.

### Production

You can call default gulp task or use `prodBuild` task to build application in production environment. 

```text
gulp 
```

or

```text
gulp prodBuild
```

In this case will be used Polymer gulp tasks with adapters and loaders to combine all components into single file. Also all code will be minifyed. At first it will clean destenation directory, than pre-build project with polytempl in separate directory, build elements using Polymer tools, remove pre-builded elements.

