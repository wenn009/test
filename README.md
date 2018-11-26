# enterprisesite-common v0.3.0

Enterprisesite Common has reusable styled components and helper functions to help us build our enterprise site project much more quickly and easier.

- [Maintainers](#maintainers)
- [Installation](#installation)
- [Running Demo Locally](#running-demo-locally)
- [Usage](#usage)
- [Make a Release](#make-a-release)
- [Undo a Release](#undo-a-release)
- [Components](#components)
- [Functions](#functions)
- [Middleware](#middleware)

## Maintainers

`web team`

## Installation

```
npm install git+ssh://git@github.com/foursquare/enterprisesite-common.git#0.3.0
```

## Running Demo Locally

```
git clone git@github.com:foursquare/enterprisesite-common.git
```

```
npm install
```

```
npm start
```

visit `localhost:3000` in your browser

## Usage

1.  import a component/function from enterprisesite-common
    ```jsx
    import { Spinner } from 'enterprisesite-common';
    ```
    or
    ```jsx
    import { changePassword } from 'enterprisesite-common';
    ```
2.  For Components, use it by passing appropriate props
    ```jsx
    <Spinner />
    ```
    For Functions, use it by passing appropriate params
    ```jsx
    changePassword(currentPassword, newPassword)
    	.then(...)
    ```

* For more usage, checkout our demo page by running the project locally.

## Make a Release

1.  Create a new branch and add your input, then create a pull request
2.  After it is approved, squash and merge into master, make a new branch to build the project by running:
    ```jsx
    npm run build
    ```
    and also change the version number in package.json
    
    see [Semantic Versioning Specification](https://semver.org/) for more information on version number
3.  Create another Pull Request and let someone to approve it before merging.
4.  Make a new release of the new version: 
    - go to https://github.com/foursquare/enterprisesite-common/releases
    - click on **Draft a new release** on the upper right hand corner
    - Input version number as the Tag version, an appropriate title, and a description describing what's new/changed

5. Click **Publish release**, Done!

## Components

Component are styled with [**styled-components**](https://www.styled-components.com/)

### <u>Highcharts</u>

| props        | propType | what is it | require? | default value |
| ------------ | -------- | ---------- | -------- | ------------- |
| type         | string   |            | no       | 'Chart'       |
| chartOptions | object   |            | no       | {}            |
| height       | string   |            | no       | -             |
| width        | string   |            | no       | -             |
| className    | string   |            | no       | ''            |

For more information, please check out: [**highcharts**](https://www.highcharts.com/)

### <u>Icon</u>

| props | propType | what is it       | require? | default value |
| ----- | -------- | ---------------- | -------- | ------------- |
| type  | string   | name of the icon | no       | -             |

To see all the icons you can use, check out: [spritesvg](https://ss0.4sqi.net/fonts/foursquare_icons/sprite.svg) or running Demo locally then click on ![all icons](https://user-images.githubusercontent.com/22780221/48790552-9fdf8480-ecbd-11e8-8c6f-682a13b26c6b.png) on the side bar.

### <u>InfoWidget</u>

| props         | propType | what is it                     | require? | default value |
| ------------- | -------- | ------------------------------ | -------- | ------------- |
| title         | node     |                                | no       | null          |
| icon          | node     |                                | no       | null          |
| expanded      | bool     |                                | no       | false         |
| onExpand      | func     |                                | no       | null          |
| disableToggle | bool     | disable sidebar from expanding | no       | false         |
| className     | string   |                                | no       | null          |
| children      | node     | content                        | no       | null          |

### <u>PageBody</u>

| props     | propType | what is it                                      | require? | default value |
| --------- | -------- | ----------------------------------------------- | -------- | ------------- |
| header    | node     | can use <PageBodyHeader /> here                 | no       | null          |
| content   | node     | main content                                    | no       | null          |
| right     | node     | content floating on the upper right hand corner | no       | null          |
| className | string   |                                                 | no       | null          |

### <u>PageBodyHeader</u>

| props     | propType | what is it                     | require? | default value |
| --------- | -------- | ------------------------------ | -------- | ------------- |
| title     | node     | title of the body              | no       | null          |
| right     | node     | subtitle floating on the right | no       | null          |
| className | string   |                                | no       | null          |

### <u>PageHeader</u>

| props     | propType | what is it                     | require? | default value |
| --------- | -------- | ------------------------------ | -------- | ------------- |
| title     | node     | title of the page              | no       | null          |
| right     | node     | subtitle floating on the right | no       | null          |
| className | string   |                                | no       | null          |

### <u>RetinaImage</u>

serving high-resolution images to devices with retina displays

| props     | propType | what is it             | require? | default value |
| --------- | -------- | ---------------------- | -------- | ------------- |
| src       | string   | regular source         | yes      | -             |
| retinaSrc | string   | high resolution source | no       | null          |
| alt       | string   |                        | no       | null          |
| width     | string   |                        | no       | null          |
| height    | string   |                        | no       | null          |
| className | string   |                        | no       | null          |

### <u>SectionTile</u>

| props                | propType | what is it                       | require? | default value                                                |
| -------------------- | -------- | -------------------------------- | -------- | ------------------------------------------------------------ |
| title                | node     | title                            | no       | null                                                         |
| boxedTitle           | bool     | ?                                | no       | true                                                         |
| right                | node     | subtitle floating on the right   | no       | null                                                         |
| body                 | node     | content                          | no       | null                                                         |
| titleBackgroundStyle | string   | value of css `background-image`, | no       | "linear-gradient(to right, #acc0ef, #d9e2f6, #e6ecff, #fff)" |
| titleColor           | string   | title's font color               | no       | "black"                                                      |
| className            | string   |                                  | no       | null                                                         |

### <u>Sidebar</u>

| props         | propType | what is it | require? | default value |
| ------------- | -------- | ---------- | -------- | ------------- |
| renderHeader  | func     |            | no       | null          |
| renderContent | func     |            | no       | null          |
| renderFooter  | func     |            | no       | null          |
| showToggle    | bool     |            | no       | true          |
| onToggle      | func     |            | no       | null          |
| className     | string   |            | no       | null          |

### <u>SidebarItem</u>

| props          | propType | what is it                                             | require? | default value |
| -------------- | -------- | ------------------------------------------------------ | -------- | ------------- |
| icon           | string   | default icon                                           | no       | null          |
| iconHover      | object   | icon on hover over                                     | no       | null          |
| label          | string   | sidebar item's label                                   | no       | null          |
| tooltipLabel   | string   | label for tooltip if is different sidebar item's label | no       | null          |
| disableTooltip | bool     |                                                        | no       | false         |
| isInHeader     | bool     |                                                        | no       | false         |
| onClick        | func     |                                                        | no       | null          |
| className      | string   |                                                        | no       | null          |

### <u>Spinner</u>

a loading spinner

| props      | propType | what is it                  | require? | default value |
| ---------- | -------- | --------------------------- | -------- | ------------- |
| height     | number   | height of Spinner's wrapper | no       | 300           |
| iconWidth  | number   |                             | no       | 32            |
| iconHeight | number   |                             | no       | 32            |
| className  | string   |                             | no       | null          |

### <u>Tile</u>

an empty Tile with showdows

| props     | propType | what is it | require? | default value |
| --------- | -------- | ---------- | -------- | ------------- |
| children  | node     | anything   | no       | null          |
| className | string   |            | no       | null          |

### <u>Tooltip</u>

a styled version of [react-tooltip](https://www.npmjs.com/package/react-tooltip).
For more advance usage, check out [**this**](https://react-tooltip.netlify.com/).

## Functions

### <u>apiAuthFetch</u>

| params                 | type    | what is it   | require? | default value |
| ---------------------- | ------- | ------------ | -------- | ------------- |
| url                    | string  | url          | yes      | -             |
| fetchOptions           | object  | fetchOptions | no       | `{}`          |
| redirectOnUnauthorized | boolean |              | no       | `true`        |

### <u>apiFetch</u>

| params       | type   | what is it   | require? | default value |
| ------------ | ------ | ------------ | -------- | ------------- |
| url          | string | url          | yes      | -             |
| fetchOptions | object | fetchOptions | no       | `{}`          |

### <u>changePassword</u>

| params      | type   | what is it | require? | default value |
| ----------- | ------ | ---------- | -------- | ------------- |
| oldPassword | string | password   | yes      | -             |
| newPassword | string | password   | yes      | -             |

### <u>getToken</u>

* returns JWT token

### <u>isLoggedIn</u>

* returns if the user is logged in

### <u>logout</u>

* async call to logout the user

### <u>logULAction</u>

> ? TO DO

### <u>sortNullValues</u>

* Use this sort method IF at least one of the values is null. This will always favor

* the actual values and push the null values down.

| params | type | what is it | require? | default value |
| ------ | ---- | ---------- | -------- | ------------- |
| aValue | any  |            | no       | null          |
| bValue | any  |            | no       | null          |

## Middleware

### <u>ULLoggingMiddleware</u>

> ? TO DO

## Undo a Release

** Be careful when you are doing this!!!! **
1.  following 'Deleting a release' on https://help.github.com/articles/editing-and-deleting-releases/
2.  to delete the local and remote tag
    ```
    git push --delete origin tagName
    ```
