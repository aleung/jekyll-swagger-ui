# Jekyll Swagger UI Plugin

[Swagger](http://swagger.io/) is a framework for describing, producing, consuming, and visualizing RESTful web APIs. It includes the Swagger Specification and a set of tools. [Swagger UI](https://github.com/swagger-api/swagger-ui) is a web tool that dynamically generate documentation from API definition file in Swagger Spec.

This plugin integrates Swagger UI into Jekyll site. API document can be generated and embedded in page or post.

## Installation

### Swagger UI

Download or clone swagger-ui code from [Swagger GitHub project](https://github.com/swagger-api/swagger-ui). Copy swagger-ui's `dist` folder to your Jekyll site and rename to `swagger-ui`.

_Note (2015-4-3)_: The latest release of swagger-ui doesn't work in Jekyll because of issue [#1069](https://github.com/swagger-api/swagger-ui/issues/1069). Before the pull request is merged and released, you can download a workable version from [here](https://github.com/aleung/swagger-ui/releases/tag/tmp_20150403). 

### Plugin

Put `swagger_ui.rb` in `/_plugins/` (for Jekyll) or `/plugins/` (for Octopress) directory.

Put `swagger.html` in `/_include` (for Jekyll) or `/source/_include` (for Octopress) directory.

Include `swagger.html` in `<head>` section of your layout file:

``` html
	<html>
	<head>
	  ...
	  {% include swagger.html %}
	</head>
```
## Usage

Put the JSON file which describes your API into your Jekyll site, e.g. put under `/api` folder.

Use `swagger` tag to embed the API document in your markdown. The parameter is the link to your API JSON file.

	{% swagger /api/my-api.json %}

