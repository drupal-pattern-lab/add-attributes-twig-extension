# add-attributes-twig-extension

Twig function that allows addition of attributes that can be rendered in both Drupal and Pattern Lab. Merges with template level attributes in Drupal and prevents them from trickling down into includes.

## Usage
```
{% set additional_attributes = {
  "class": ["foo", "bar"],
  "baz": ["foobar", "goobar"],
  "foobaz": "goobaz",
} %}

<div {{ add_attributes(additional_attributes) }}></div>
```

Can also be used with the [bem function](https://github.com/drupal-pattern-lab/bem-twig-extension):
```
{% set additional_attributes = {
  "class": bem("foo", ["bar", "baz"], "foobar"),
} %}

<div {{ add_attributes(additional_attributes) }}></div>
```

Can also be used with title_attributes or content_attributes:
```
{% set additional_title_attributes = {
  "class": ["foo__title", "bar__title"],
} %}
{% set additional_content_attributes = {
  "class": ["foo__content", "bar__content"],
} %}

<h2 {{ add_attributes(additional_title_attributes,'title_attributes') }}></h2>
<div {{ add_attributes(additional_content_attributes,'content_attributes') }}>

```