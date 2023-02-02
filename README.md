# Learn by making prototype kit

This prototype kit is based on the [GOV.UK prototype kit](https://github.com/alphagov/govuk-prototype-kit) with a few tweaks.

### Requirements

* access to commandline (terminal on mac, [Git Bash](https://git-scm.com/download/win) on Windows)
* node 18+

## Getting started

Install kit by running

```
npm install
```

Start the application by running

```
npm start
```

## Bilingual prototypes

Currently, it is a bit clunky but you can still do it.

By default the prototype banner has a language switcher button. It is disabled until you hook up the right pages.

Firstly, make sure you have 2 pages, one for the English version and one for the Welsh version.

Need to overwrite the `header` block in both.

In the English page put

```
{% block header %}
  {{ prototypeHeader({
    "lang": "en",
    "alternative": {
      "href": "link to welsh version"
    }
  }) }}
{% endblock %}
```

In the Welsh page put

```
{% block header %}
  {{ prototypeHeader({
    "lang": "cy",
    "alternative": {
      "href": "link to english version"
    }
  }) }}
{% endblock %}
```

There is an example start page in the `app/views/examples` folder.

## Work in progress

It is early days for this prototype kit.

A few things we'd like to work on include:

* making it easier to create bilingual prototypes (can we use a config file for common site wide translations?)
* reduce the references to `govuk` e.g. in class names. We want to do this to reduce complexity for users and to make the prototype kit feel more general purpose than govuk owned.
* work out how to add Wales specific components when they get produced