---
layout: page
title: Theme API
permalink: /theme-api/
---

## General

Item                   | Description
-----------------------|--------------
`su.calendar.events`   | `event.id`, `event.title`, `event.description`, `event.start`, `event.end`, `event.location`, `event.isAllDay`
`su.content`           |
`su.footer`            |
`su.misc.privatelabel` | Retrieve site's private label

## su.editable

Item                                        | Description
--------------------------------------------|--------------------------------------------------
`su.editable.region( (string) identifier )` | Allows inline editing of a custom content region
`su.editable.title`                         | Allows inline editing of page title

## su.page

Item                      | Description
--------------------------|-------------------------------         
`su.page("/url")`         | Get page by path
`su.page.authors`         |
`su.page.breadcrumbs`     |
`su.page.children`        | Get a page's children
`su.page.children(id)`    | Get the children of a specific page. Inspect the table row in the admin page list to get the id.
`su.page.content`         | Allows for things like `{{ child.description ?: child.content\|striptags\|pretty_truncate(200) }}`
`su.page.description`     |
`su.page.featuredImage`   | `.fit(x,y)`, `.fill(x,y)`, `.ratio(x,y)`
`su.page.navigationLabel` |
`su.page.parent`          | Parent of current page
`su.page.posts`           | Get the posts associated with a blog page. Posts have the same content as pages (title, etc).
`su.page.publishedAt`     | To format in Twig: {% raw %}`{{ su.page.publishedAt|date( "F j, Y" ) }}`{% endraw %}
`su.page.target`          |
`su.page.thumbnail`       |
`su.page.title`           | Does not allow inline editing
`su.page.topParent`       | Top parent of current page
`su.page.updatedAt`       | To format in Twig: {% raw %}`{{ su.page.updatedAt|date( "F j, Y" ) }}`{% endraw %}
`su.page.url`             |

## su.request

Item                    | Description
------------------------|-------------
`su.request.path`       |
`su.request.protocol`   |
`su.request.query`      | Allows access to POST and GET data
`su.request.serverName` |
`su.request.url`        |

## su.site

Item                 | Description
---------------------|--------------
`su.site.address`    |
`su.site.city`       |
`su.site.country`    |
`su.site.logo`       | `.fit(x,y)`, `.fill(x,y)`, `.ratio(x,y)`
`su.site.name`       | Website name
`su.site.navigation` | `item.name`, `item.url`, `item.target`, `item.current`, `item.hasParent`, `item.hasChildren`
`su.site.phone`      |
`su.site.secondline` | Website slogan
`su.site.state`      |
`su.site.url`        | Website's primary URL
`su.site.zip`        |

## su.theme

Item                                     | Description
-----------------------------------------|--------------------------------
`su.theme.asset( (string) path )`        | Path in theme's `asset/` folder
`su.theme.config( (string) identifier )` | Retrieve theme config value
`su.theme.css( (string) path )`          | Path in theme's `style/` folder
`su.theme.js( (string) path )`           | Path in theme's `script/` folder

## su.user

Item                 | Description
---------------------|--------------
`su.user.first_name` |
`su.user.is_admin`   | Boolean
`su.user.last_name`  |
