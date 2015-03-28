# Designers Guide

You're a designer and want to publish your design on the WUNDERY platform?

* Contact us (support@wundery.com)
* Get a free sandbox store
* Build your design
* Publish on the WUNDERY Platform
* Earn money

## Required files

Only one file is required: the design master. You may choose an arbitray name, e.g. `master.html` or `index.html` but make sure to set it as master file in the WUNDERY designer.

## Design configuration

To make your design easily customizable for the store owner, you may create a so called manifest file in the JSON format. Name it as you like, e.g. `design.json`, but make sure to set it as manifest file within the designer. The following example shows the available options:

```json
{
  "options": [
    {
      "name": "background_color",
      "type": "color",
      "default_value": "#c5c5c5",
      "title": {
        "de": "Hintergrundfarbe",
        "en": "Background color"
      },
      "description": {
        "de": "Hintergrundfarbe aller Shopseiten",
        "en": "Background color of all store pages"
      }
    },
    {
      "name": "link_color",
      "type": "color",
      "default_value": "#000",
      "title": "Link color",
      "description": "Background color of all store pages"
    }
  ]
}
```

**IMPORTANT** - Your manifest file must contain valid JSON. If it does not, no option at all will be shown to the store owner. We recommend using a validator, e.g. http://jsonlint.com.

The top-level structure of the manifest file is defined as follows:

| Key | Description          |
| :------------- | :----------- |
| options | Array of available customization options |

Every option has the following structure:

| Key | Description          |
| :------------- | :----------- |
| name | A unique name for the option. It's used for fetching the options value in the designs source, e.g. `{% setting 'background_color' %}` |
| type | The options type. Supported: **color** (shows a color picker) |
| default_value | The options default value. This will be used if the user did not define another value. |
| title | A short explanation of the option that will be displayed in the user interface. If it is defined as a string, it is assumed to be the english title. Otherwise it is assumed to be a hash containing locales as keys and translated titles as values. The following values are both valid: `"title": "..."` or `"title": { "de": "...", "en": "...", ... }` |
| description | Same as title but used for a longer explanation |

## Template reference

### Liquid

You can use the following tags:

#### General store attributes

* `{{ store.id }}`
* `{{ store.title }}`
* `{{ store.description }}`
* `{{ store.description_sanitized }}`
* `{{ store.slogan }}`
* `{{ store.facebook_url }}`
* `{{ store.pinterest_url }}`
* `{{ store.twitter_url }}`
* `{{ store.google_analytics_id }}`
* `{{ store.display_net }}`
* `{{ store.url }}`
* `{{ store.description }}`
* `{{ store.locale }}`

#### Objects and collections on the store

* `{{ store.homepage_category }}`
* `{{ store.homepage_products }}`
* `{{ store.categories }}`
* `{{ store.pages }}`
* `{{ store.payment_methods }}`
* `{{ store.shipping_methods }}`
* `{{ store.logo }}`