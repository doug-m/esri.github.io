# esri.github.io

> Landing page for all of our projects.

Both the project categories and search suggestions in http://esri.github.io are powered by GitHub [topics](https://github.com/blog/2309-introducing-topics).

<kbd>web-development</kbd> <kbd>data-management</kbd> <kbd>spatial-analysis</kbd> <kbd>publishing-sharing</kbd> <kbd>native-development</kbd>

You can find a complete list of searchable topics in [`search-topics.yml`](src/data/search-topics.yml). When a [topic](https://github.com/blog/2309-introducing-topics) is added to an Esri repository, it will be reflected in search immediately.

## Development

The website is generated using the open source static site generator [`acetate`](https://github.com/patrickarlt/acetate) and styled with the help of [`calcite-web`](https:esri.github.io/calcite-web/).

1. Fork and clone the project
2. Install the [`package.json`](package.json) dependencies by running `npm install`
3. Run `npm start`. This will generate built pages in memory, launch the site on http://localhost:8000 and watch the raw source for changes.
4. To create a build that will be saved to disk, use `grunt build`

## Architecture

Information for the case studies and featured projects can be found in [`projects.yml`](src/data/projects.yml)

```yaml
- title: R Analysis
    description: Develop and share R statistical analysis with ArcGIS.
    image: //developers.arcgis.com/assets/img/homepage/promo-python.png
    url: //r-arcgis.github.io/
    displayLang: R
    searchLang: r
    stars: 47
```

Templated markup for the featured content is located in [`_macros.html`](src/layouts/_macros.html)

For example, below we define a loop to generate 24 cards using information from `projects.yml`
```html
<div class="block-group block-group-4-up tablet-block-group-2-up phone-block-group-1-up">
    {% for project in projectInfo.projects %}
    {% if loop.index > 1 %}
    <div class="card block leader-1">
        <div class="card-content card-bar-{{ projectInfo.color }}">
        <h4>{{ project.title }}</h4>
        <p class="card-last">{{ project.description }}</p>
        <!-- ... -->
        </div>
    </div>
    {% endif %}
    {% endfor %}
    </div>
```
A bare minimum of `<html>` scaffolding can be found in [`src/index.html`](https://github.com/Esri/esri.github.io/blob/master/src/index.html)

## Contributing

Anyone and everyone is welcome to contribute. Please see our [guidelines for contributing](https://github.com/esri/contributing).

## Licensing

Copyright 2017 Esri

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

A copy of the license is available in the repository's [LICENSE]( https://raw.github.com/Esri/esri.github.com/master/license.txt) file.