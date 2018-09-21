# Module structure

## Files structure

{% tabs %}
{% tab title="application\_root/:" %}
I  
- `.circleci/`   
- `gulp-tasks/`   
- `images/`   
- `src/`   
        I  
        - `elements/`   
- `tests/`   
- `index.html`   
- `package.json`   
- `bower.json`   
- `polymer.json`   
- ...Other configuration files
{% endtab %}
{% endtabs %}

In the application root directory you can find all configuration files for development and build process. Here you can find Docker config files, configs for code linting, tests, gulp config, node server. Code for gulp tasks is placed in  `gulp-tasks/` directory. You can find all application elements in `src/elements/` directory. In `tests/` directory you can find entry point for tests.

## Elements directory structure

{% tabs %}
{% tab title="application\_root/src/elements/ :" %}
I  
- `app-mixins/`   
- `common-elements/`   
- `core-elements/`   
        I  
        - `app-config/`   
        - `app-shell/` \(main application component\)  
        - `app-main-header/`   
        - `app-sidebar/`   
- `data-elements/`    
- `pages/`   
        I  
        - `action-points-page-components/`   
        - `not-found-page-view/`   
- `styles-elements/` 
{% endtab %}
{% endtabs %}

In `elements/` you can find:

1. `app-mixins/` directory with all application mixins \(permission, common-methods, error-handler and ect.\)
2. `common-elements/` directory with elements that are used in different pages several times
3. `core-elements/` directory with application config element, application main element and base elements common to all modules \(header, sidebar\)
4. `data-elements/`  directory with elements used to request static data from server \(user-data, static-data\)
5. `pages/` directory with elements divided by pages, which will be lazy loaded
6. `styles-elements/` with common styles elements

## Component structure

Almost all application components are split into 3 separate files: 

* html file with component template
* js file with components logic
* scss file with component styles

### Polytempl

Polytempl plugin helps combine separate components files and resolve imports.

You need to specify the special html comment to combine your html template file with js and scss files:

```text
<!-- inject styles './path_to_styles.scss'-->
```

or 

```text
<!-- inject scripts './path_to_logic.js'-->
```

You can specify the special html comment for imports. Polytempl will look for this components in your src files at first and than in `bower_components/` . See more details about Polytempl [here](https://www.npmjs.com/package/polytempl).

```text
<!--import [polymer]-->
<!--import [module-styles, page-layout-styles, shared-styles, list-tab-main,
            static-data-behavior, search-and-filter, engagements-list-data, 
            pages-header-element, permission-controller, etools-app-config]-->
```

