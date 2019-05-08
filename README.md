# ![LOGO](logo.png) Wikimedia **flow**ground Connector

## Description

A generated **flow**ground connector for the Wikimedia API (version 1.0.0).

Generated from: https://api.apis.guru/v2/specs/wikimedia.org/1.0.0/swagger.json<br/>
Generated at: 2019-05-07T17:44:55+03:00

## API Description

This API provides cacheable and straightforward access to Wikimedia content and data, in machine-readable formats.
### Global Rules
- Limit your clients to no more than 200 requests/s to this API.
  Each API endpoint's documentation may detail more specific usage limits.
- Set a unique `User-Agent` or `Api-User-Agent` header that
  allows us to contact you quickly. Email addresses or URLs
  of contact pages work well.

By using this API, you agree to Wikimedia's  [Terms of Use](https://wikimediafoundation.org/wiki/Terms_of_Use) and [Privacy Policy](https://wikimediafoundation.org/wiki/Privacy_policy). Unless otherwise specified in the endpoint documentation below, content accessed via this API is licensed under the [CC-BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/)  and [GFDL](https://www.gnu.org/copyleft/fdl.html) licenses, and you irrevocably agree to release modifications or additions made through this API under these licenses.  See https://www.mediawiki.org/wiki/REST_API for background and details.
### Endpoint documentation
Please consult each endpoint's documentation for details on:
- Licensing information for the specific type of content
  and data served via the endpoint.
- Stability markers to inform you about development status and
  change policy, according to
  [our API version policy](https://www.mediawiki.org/wiki/API_versioning).
- Endpoint specific usage limits.


## Authorization

Supported authorization schemes:
- API Key
## Actions

### Gets availability of featured feed content for the apps by wiki domain.

> Gets availability of featured feed content for the apps by wiki domain.<br/>
> <br/>
> Stability: [experimental](https://www.mediawiki.org/wiki/API_versioning#Experimental)

*Tags:* `Feed content availability`

### Check and normalize a TeX formula.

> Checks the supplied TeX formula for correctness and returns the<br/>
> normalised formula representation as well as information about<br/>
> identifiers. Available types are tex and inline-tex. The response<br/>
> contains the `x-resource-location` header which can be used to retrieve<br/>
> the render of the checked formula in one of the supported rendering<br/>
> formats. Just append the value of the header to `/media/math/{format}/`<br/>
> and perform a GET request against that URL.<br/>
> <br/>
> Stability: [stable](https://www.mediawiki.org/wiki/API_versioning#Stable).

*Tags:* `Math`

#### Input Parameters
* `type` - _required_ - The input type of the given formula; can be tex or inline-tex
    Possible values: tex, inline-tex, chem.

### Get a previously-stored formula

> Returns the previously-stored formula via `/media/math/check/{type}` for<br/>
> the given hash.<br/>
> <br/>
> Stability: [stable](https://www.mediawiki.org/wiki/API_versioning#Stable).

*Tags:* `Math`

#### Input Parameters
* `hash` - _required_ - The hash string of the previous POST data

### Get rendered formula in the given format.

> Given a request hash, renders a TeX formula into its mathematic<br/>
> representation in the given format. When a request is issued to the<br/>
> `/media/math/check/{format}` POST endpoint, the response contains the<br/>
> `x-resource-location` header denoting the hash ID of the POST data. Once<br/>
> obtained, this endpoint has to be used to obtain the actual render.<br/>
> <br/>
> Stability: [stable](https://www.mediawiki.org/wiki/API_versioning#Stable).

*Tags:* `Math`

#### Input Parameters
* `format` - _required_ - The output format; can be svg or mml
    Possible values: svg, mml, png.
* `hash` - _required_ - The hash string of the previous POST data

### Get the sum of absolute value of text bytes difference between current edit and<br/>
> previous one.

> Given a Mediawiki project and a date range, returns a timeseries of absolute bytes<br/>
> difference sums. You can filter by editors-type (all-editor-types, anonymous, group-bot,<br/>
> name-bot, user) and page-type (all-page-types, content, non-content). You can choose<br/>
> between daily and monthly granularity as well.<br/>
> <br/>
> - Stability: [experimental](https://www.mediawiki.org/wiki/API_versioning#Experimental)<br/>
> - Rate limit: 25 req/s<br/>
> - License: Data accessible via this endpoint is available under the<br/>
>   [CC0 1.0 license](https://creativecommons.org/publicdomain/zero/1.0/).

*Tags:* `Bytes difference data`

#### Input Parameters
* `project` - _required_ - The name of any Wikimedia project formatted like {language code}.{project name},
for example en.wikipedia. You may pass en.wikipedia.org and the .org will be stripped
off. For projects like commons without language codes, use commons.wikimedia. For
projects like www.mediawiki.org, you can use that full string, or just use mediawiki
or mediawiki.org. If you're interested in the aggregation of all projects, use
all-projects.

* `editor-type` - _required_ - If you want to filter by editor-type, use one of anonymous, group-bot (registered
accounts belonging to the bot group), name-bot (registered accounts not belonging to
the bot group but having bot-like names) or user (registered account not in bot group
nor having bot-like name). If you are interested in edits regardless of their
editor-type, use all-editor-types.

    Possible values: all-editor-types, anonymous, group-bot, name-bot, user.
* `page-type` - _required_ - If you want to filter by page-type, use one of content (edits on pages in content
namespaces) or non-content (edits on pages in non-content namespaces). If you are
interested in edits regardless of their page-type, use all-page-types.

    Possible values: all-page-types, content, non-content.
* `granularity` - _required_ - Time unit for the response data. As of today, supported values are daily and monthly

    Possible values: daily, monthly.
* `start` - _required_ - The date of the first day to include, in YYYYMMDD format
* `end` - _required_ - The date of the last day to include, in YYYYMMDD format

### Get the sum of absolute text bytes difference per page.

> Given a Mediawiki project, a page-title prefixed with canonical namespace (for<br/>
> instance 'User:Jimbo_Wales') and a date range, returns a timeseries of bytes<br/>
> difference absolute sums. You can filter by editors-type (all-editor-types, anonymous,<br/>
> group-bot, name-bot, user). You can choose between daily and monthly granularity as well.<br/>
> <br/>
> - Stability: [experimental](https://www.mediawiki.org/wiki/API_versioning#Experimental)<br/>
> - Rate limit: 25 req/s<br/>
> - License: Data accessible via this endpoint is available under the<br/>
>   [CC0 1.0 license](https://creativecommons.org/publicdomain/zero/1.0/).

*Tags:* `Bytes difference data`

#### Input Parameters
* `project` - _required_ - The name of any Wikimedia project formatted like {language code}.{project name},
for example en.wikipedia. You may pass en.wikipedia.org and the .org will be stripped
off. For projects like commons without language codes, use commons.wikimedia. For
projects like www.mediawiki.org, you can use that full string, or just use mediawiki
or mediawiki.org.

* `page-title` - _required_ - The page-title to request absolute bytes-difference for. Should be prefixed with the
page canonical namespace.

* `editor-type` - _required_ - If you want to filter by editor-type, use one of anonymous, group-bot (registered
accounts belonging to the bot group), name-bot (registered accounts not belonging to
the bot group but having bot-like names) or user (registered account not in bot group
nor having bot-like name). If you are interested in edits regardless of their
editor-type, use all-editor-types.

    Possible values: all-editor-types, anonymous, group-bot, name-bot, user.
* `granularity` - _required_ - Time unit for the response data. As of today, supported values are daily and monthly

    Possible values: daily, monthly.
* `start` - _required_ - The date of the first day to include, in YYYYMMDD format
* `end` - _required_ - The date of the last day to include, in YYYYMMDD format

### Get the sum of net text bytes difference between current edit and previous one.

> Given a Mediawiki project and a date range, returns a timeseries of bytes difference net<br/>
> sums. You can filter by editors-type (all-editor-types, anonymous, group-bot, name-bot,<br/>
> user) and page-type (all-page-types, content or non-content). You can choose between<br/>
> daily and monthly granularity as well.<br/>
> <br/>
> - Stability: [experimental](https://www.mediawiki.org/wiki/API_versioning#Experimental)<br/>
> - Rate limit: 25 req/s<br/>
> - License: Data accessible via this endpoint is available under the<br/>
>   [CC0 1.0 license](https://creativecommons.org/publicdomain/zero/1.0/).

*Tags:* `Bytes difference data`

#### Input Parameters
* `project` - _required_ - The name of any Wikimedia project formatted like {language code}.{project name},
for example en.wikipedia. You may pass en.wikipedia.org and the .org will be stripped
off. For projects like commons without language codes, use commons.wikimedia. For
projects like www.mediawiki.org, you can use that full string, or just use mediawiki
or mediawiki.org. If you're interested in the aggregation of all projects, use
all-projects.

* `editor-type` - _required_ - If you want to filter by editor-type, use one of anonymous, group-bot (registered
accounts belonging to the bot group), name-bot (registered accounts not belonging to
the bot group but having bot-like names) or user (registered account not in bot group
nor having bot-like name). If you are interested in edits regardless of their
editor-type, use all-editor-types.

    Possible values: all-editor-types, anonymous, group-bot, name-bot, user.
* `page-type` - _required_ - If you want to filter by page-type, use one of content (edits on pages in content
namespaces) or non-content (edits on pages in non-content namespaces). If you are
interested in edits regardless of their page-type, use all-page-types.

    Possible values: all-page-types, content, non-content.
* `granularity` - _required_ - Time unit for the response data. As of today, supported values are daily and monthly

    Possible values: daily, monthly.
* `start` - _required_ - The date of the first day to include, in YYYYMMDD format
* `end` - _required_ - The date of the last day to include, in YYYYMMDD format

### Get the sum of net text bytes difference per page.

> Given a Mediawiki project, a page-title prefixed with canonical namespace (for<br/>
> instance 'User:Jimbo_Wales') and a date range, returns a timeseries of bytes<br/>
> difference net sums. You can filter by editors-type (all-editor-types, anonymous,<br/>
> group-bot, name-bot, user). You can choose between daily and monthly granularity as well.<br/>
> <br/>
> - Stability: [experimental](https://www.mediawiki.org/wiki/API_versioning#Experimental)<br/>
> - Rate limit: 25 req/s<br/>
> - License: Data accessible via this endpoint is available under the<br/>
>   [CC0 1.0 license](https://creativecommons.org/publicdomain/zero/1.0/).

*Tags:* `Bytes difference data`

#### Input Parameters
* `project` - _required_ - The name of any Wikimedia project formatted like {language code}.{project name},
for example en.wikipedia. You may pass en.wikipedia.org and the .org will be stripped
off. For projects like commons without language codes, use commons.wikimedia. For
projects like www.mediawiki.org, you can use that full string, or just use mediawiki
or mediawiki.org.

* `page-title` - _required_ - The page-title to request net bytes-difference for. Should be prefixed with the
page canonical namespace.

* `editor-type` - _required_ - If you want to filter by editor-type, use one of anonymous, group-bot (registered
accounts belonging to the bot group), name-bot (registered accounts not belonging to
the bot group but having bot-like names) or user (registered account not in bot group
nor having bot-like name). If you are interested in edits regardless of their
editor-type, use all-editor-types.

    Possible values: all-editor-types, anonymous, group-bot, name-bot, user.
* `granularity` - _required_ - Time unit for the response data. As of today, supported values are daily and monthly

    Possible values: daily, monthly.
* `start` - _required_ - The date of the first day to include, in YYYYMMDD format
* `end` - _required_ - The date of the last day to include, in YYYYMMDD format

### Get edited-pages counts for a project.

> Given a Mediawiki project and a date range, returns a timeseries of its edited-pages counts.<br/>
> You can filter by editor-type (all-editor-types, anonymous, group-bot, name-bot, user),<br/>
> page-type (all-page-types, content or non-content) or activity-level (1..4-edits,<br/>
> 5..24-edits, 25..99-edits, 100..-edits). You can choose between daily and monthly<br/>
> granularity as well.<br/>
> <br/>
> - Stability: [experimental](https://www.mediawiki.org/wiki/API_versioning#Experimental)<br/>
> - Rate limit: 25 req/s<br/>
> - License: Data accessible via this endpoint is available under the<br/>
>   [CC0 1.0 license](https://creativecommons.org/publicdomain/zero/1.0/).

*Tags:* `Edited pages data`

#### Input Parameters
* `project` - _required_ - The name of any Wikimedia project formatted like {language code}.{project name},
for example en.wikipedia. You may pass en.wikipedia.org and the .org will be stripped
off.  For projects like commons without language codes, use commons.wikimedia.
For projects like www.mediawiki.org, you can use that full string, or just use
mediawiki or mediawiki.org.

* `editor-type` - _required_ - If you want to filter by editor-type, use one of anonymous, group-bot (registered
accounts belonging to the bot group), name-bot (registered accounts not belonging to
the bot group but having bot-like names) or user (registered account not in bot group
nor having bot-like name). If you are interested in edits regardless of their
editor-type, use all-editor-types.

    Possible values: all-editor-types, anonymous, group-bot, name-bot, user.
* `page-type` - _required_ - If you want to filter by page-type, use one of content (edited-pages in content
namespaces) or non-content (edited-pages in non-content namespaces). If you are
interested in edited-pages regardless of their page-type, use all-page-types.

    Possible values: all-page-types, content, non-content.
* `activity-level` - _required_ - If you want to filter by activity-level, use one of 1..4-edits, 5..24-edits,
25..99-edits or 100..-edits. If you are interested in edited-pages regardless
of their activity level, use all-activity-levels.

    Possible values: all-activity-levels, 1..4-edits, 5..24-edits, 25..99-edits, 100..-edits.
* `granularity` - _required_ - The time unit for the response data. As of today, supported values are
daily and monthly.

    Possible values: daily, monthly.
* `start` - _required_ - The date of the first day to include, in YYYYMMDD format
* `end` - _required_ - The date of the last day to include, in YYYYMMDD format

### Get new pages counts for a project.

> Given a Mediawiki project and a date range, returns a timeseries of its new pages counts.<br/>
> You can filter by editor type (all-editor-types, anonymous, group-bot, name-bot, user)<br/>
> or page-type (all-page-types, content or non-content). You can choose between daily and<br/>
> monthly granularity as well.<br/>
> <br/>
> - Stability: [experimental](https://www.mediawiki.org/wiki/API_versioning#Experimental)<br/>
> - Rate limit: 25 req/s<br/>
> - License: Data accessible via this endpoint is available under the<br/>
>   [CC0 1.0 license](https://creativecommons.org/publicdomain/zero/1.0/).

*Tags:* `Edited pages data`

#### Input Parameters
* `project` - _required_ - The name of any Wikimedia project formatted like {language code}.{project name},
for example en.wikipedia. You may pass en.wikipedia.org and the .org will be stripped
off.  For projects like commons without language codes, use commons.wikimedia.
For projects like www.mediawiki.org, you can use that full string, or just use
mediawiki or mediawiki.org. If you're interested in the aggregation of all
projects, use all-projects.

* `editor-type` - _required_ - If you want to filter by editor-type, use one of anonymous, group-bot (registered
accounts belonging to the bot group), name-bot (registered accounts not belonging
to the bot group but having bot-like names) or user (registered account not in bot
group nor having bot-like name). If you are interested in edits regardless of
their editor-type, use all-editor-types.

    Possible values: all-editor-types, anonymous, group-bot, name-bot, user.
* `page-type` - _required_ - If you want to filter by page-type, use one of content (new pages in content
namespaces) or non-content (new pages in non-content namespaces). If you are
interested in new-articles regardless of their page-type, use all-page-types.

    Possible values: all-page-types, content, non-content.
* `granularity` - _required_ - The time unit for the response data. As of today, supported values are
daily and monthly.

    Possible values: daily, monthly.
* `start` - _required_ - The date of the first day to include, in YYYYMMDD format
* `end` - _required_ - The date of the last day to include, in YYYYMMDD format

### Get top 100 edited-pages by absolute bytes-difference.

> Given a Mediawiki project and a date (day or month), returns a timeseries of the top 100<br/>
> edited-pages by absolute bytes-difference. You can filter by editor-type (all-editor-types,<br/>
> anonymous, group-bot, name-bot, user) or page-type (all-page-types, content or non-content).<br/>
> <br/>
> - Stability: [experimental](https://www.mediawiki.org/wiki/API_versioning#Experimental)<br/>
> - Rate limit: 25 req/s<br/>
> - License: Data accessible via this endpoint is available under the<br/>
>   [CC0 1.0 license](https://creativecommons.org/publicdomain/zero/1.0/).

*Tags:* `Edited pages data`

#### Input Parameters
* `project` - _required_ - The name of any Wikimedia project formatted like {language code}.{project name},
for example en.wikipedia. You may pass en.wikipedia.org and the .org will be stripped
off. For projects like commons without language codes, use commons.wikimedia. For
projects like www.mediawiki.org, you can use that full string, or just use mediawiki
or mediawiki.org.

* `editor-type` - _required_ - If you want to filter by editor-type, use one of anonymous, group-bot (registered
accounts belonging to the bot group), name-bot (registered accounts not belonging to
the bot group but having bot-like names) or user (registered account not in bot group
nor having bot-like name). If you are interested in edits regardless of their
editor-type, use all-editor-types.

    Possible values: all-editor-types, anonymous, group-bot, name-bot, user.
* `page-type` - _required_ - If you want to filter by page-type, use one of content (edits on pages in content
namespaces) or non-content (edits on pages in non-content namespaces). If you are
interested in edits regardless of their page-type, use all-page-types.

    Possible values: all-page-types, content, non-content.
* `year` - _required_ - The year of the date for which to retrieve top edited-pages, in YYYY format.
* `month` - _required_ - The month of the date for which to retrieve top edited-pages, in MM format. If you want to get the top edited-pages of a whole month, the day parameter should be all-days.
* `day` - _required_ - The day of the date for which to retrieve top edited-pages, in DD format, or all-days for a monthly value.

### Get top 100 edited-pages by edits count.

> Given a Mediawiki project and a date (day or month), returns a timeseries of the top<br/>
> 100 edited-pages by edits count. You can filter by editor-type (all-editor-types,<br/>
> anonymous, group-bot, name-bot, user) or page-type (all-page-types, content or<br/>
> non-content).<br/>
> <br/>
> - Stability: [experimental](https://www.mediawiki.org/wiki/API_versioning#Experimental)<br/>
> - Rate limit: 25 req/s<br/>
> - License: Data accessible via this endpoint is available under the<br/>
>   [CC0 1.0 license](https://creativecommons.org/publicdomain/zero/1.0/).

*Tags:* `Edited pages data`

#### Input Parameters
* `project` - _required_ - The name of any Wikimedia project formatted like {language code}.{project name},
for example en.wikipedia. You may pass en.wikipedia.org and the .org will be stripped
off. For projects like commons without language codes, use commons.wikimedia. For
projects like www.mediawiki.org, you can use that full string, or just use mediawiki
or mediawiki.org.

* `editor-type` - _required_ - If you want to filter by editor-type, use one of anonymous, group-bot (registered
accounts belonging to the bot group), name-bot (registered accounts not belonging to
the bot group but having bot-like names) or user (registered account not in bot group
nor having bot-like name). If you are interested in edits regardless of their
editor-type, use all-editor-types.

    Possible values: all-editor-types, anonymous, group-bot, name-bot, user.
* `page-type` - _required_ - If you want to filter by page-type, use one of content (edits on pages in content
namespaces) or non-content (edits on pages in non-content namespaces). If you are
interested in edits regardless of their page-type, use all-page-types.

    Possible values: all-page-types, content, non-content.
* `year` - _required_ - The year of the date for which to retrieve top edited-pages, in YYYY format.
* `month` - _required_ - The month of the date for which to retrieve top edited-pages, in MM format. If you want to get the top edited-pages of a whole month, the day parameter should be all-days.
* `day` - _required_ - The day of the date for which to retrieve top edited-pages, in DD format, or all-days for a monthly value.

### Get top 100 edited-pages by net bytes-difference.

> Given a Mediawiki project and a date (day or month), returns a timeseries of the top 100<br/>
> edited-pages by net bytes-difference. You can filter by editor-type (all-editor-types,<br/>
> anonymous, group-bot, name-bot, user) or page-type (all-page-types, content or non-content).<br/>
> <br/>
> - Stability: [experimental](https://www.mediawiki.org/wiki/API_versioning#Experimental)<br/>
> - Rate limit: 25 req/s<br/>
> - License: Data accessible via this endpoint is available under the<br/>
>   [CC0 1.0 license](https://creativecommons.org/publicdomain/zero/1.0/).

*Tags:* `Edited pages data`

#### Input Parameters
* `project` - _required_ - The name of any Wikimedia project formatted like {language code}.{project name},
for example en.wikipedia. You may pass en.wikipedia.org and the .org will be stripped
off. For projects like commons without language codes, use commons.wikimedia. For
projects like www.mediawiki.org, you can use that full string, or just use mediawiki
or mediawiki.org.

* `editor-type` - _required_ - If you want to filter by editor-type, use one of anonymous, group-bot (registered
accounts belonging to the bot group), name-bot (registered accounts not belonging to
the bot group but having bot-like names) or user (registered account not in bot group
nor having bot-like name). If you are interested in edits regardless of their
editor-type, use all-editor-types.

    Possible values: all-editor-types, anonymous, group-bot, name-bot, user.
* `page-type` - _required_ - If you want to filter by page-type, use one of content (edits on pages in content
namespaces) or non-content (edits on pages in non-content namespaces). If you are
interested in edits regardless of their page-type, use all-page-types.

    Possible values: all-page-types, content, non-content.
* `year` - _required_ - The year of the date for which to retrieve top edited-pages, in YYYY format.
* `month` - _required_ - The month of the date for which to retrieve top edited-pages, in MM format. If you want to get the top edited-pages of a whole month, the day parameter should be all-days.
* `day` - _required_ - The day of the date for which to retrieve top edited-pages, in DD format, or all-days for a monthly value.

### Get editors counts for a project.

> Given a Mediawiki project and a date range, returns a timeseries of its editors counts.<br/>
> You can filter by editory-type (all-editor-types, anonymous, group-bot, name-bot, user),<br/>
> page-type (all-page-types, content or non-content) or activity-level (1..4-edits,<br/>
> 5..24-edits, 25..99-edits or 100..-edits). You can choose between daily and monthly<br/>
> granularity as well.<br/>
> <br/>
> - Stability: [experimental](https://www.mediawiki.org/wiki/API_versioning#Experimental)<br/>
> - Rate limit: 25 req/s<br/>
> - License: Data accessible via this endpoint is available under the<br/>
>   [CC0 1.0 license](https://creativecommons.org/publicdomain/zero/1.0/).

*Tags:* `Editors data`

#### Input Parameters
* `project` - _required_ - The name of any Wikimedia project formatted like {language code}.{project name},
for example en.wikipedia. You may pass en.wikipedia.org and the .org will be stripped
off.  For projects like commons without language codes, use commons.wikimedia.
For projects like www.mediawiki.org, you can use that full string, or just use
mediawiki or mediawiki.org.

* `editor-type` - _required_ - If you want to filter by editor-type, use one of anonymous, group-bot (registered
accounts belonging to the bot group), name-bot (registered accounts not belonging
to the bot group but having bot-like names) or user (registered account not in bot
group nor having bot-like name). If you are interested in edits regardless
of their editor-type, use all-editor-types.

    Possible values: all-editor-types, anonymous, group-bot, name-bot, user.
* `page-type` - _required_ - If you want to filter by page-type, use one of content (edits made in content
namespaces) or non-content (edits made in non-content namespaces). If you are
interested in editors regardless of their page-type, use all-page-types.

    Possible values: all-page-types, content, non-content.
* `activity-level` - _required_ - If you want to filter by activity-level, use one of 1..4-edits, 5..24-edits,
25..99-edits or 100..-edits. If you are interested in editors regardless
of their activity-level, use all-activity-levels.

    Possible values: all-activity-levels, 1..4-edits, 5..24-edits, 25..99-edits, 100..-edits.
* `granularity` - _required_ - The time unit for the response data. As of today, supported values are
daily and monthly.

    Possible values: daily, monthly.
* `start` - _required_ - The date of the first day to include, in YYYYMMDD format
* `end` - _required_ - The date of the last day to include, in YYYYMMDD format

### Get top 100 editors by absolute bytes-difference.

> Given a Mediawiki project and a date (day or month), returns a timeseries of the top 100<br/>
> editors by absolute bytes-difference. You can filter by editor-type (all-editor-types,<br/>
> anonymous, group-bot, name-bot, user) or page-type (all-page-types, content or non-content).<br/>
> The user_text returned is either the mediawiki user_text if the user is registered, or<br/>
> null if user is anonymous.<br/>
> <br/>
> - Stability: [experimental](https://www.mediawiki.org/wiki/API_versioning#Experimental)<br/>
> - Rate limit: 25 req/s<br/>
> - License: Data accessible via this endpoint is available under the<br/>
>   [CC0 1.0 license](https://creativecommons.org/publicdomain/zero/1.0/).

*Tags:* `Editors data`

#### Input Parameters
* `project` - _required_ - The name of any Wikimedia project formatted like {language code}.{project name},
for example en.wikipedia. You may pass en.wikipedia.org and the .org will be stripped
off. For projects like commons without language codes, use commons.wikimedia. For
projects like www.mediawiki.org, you can use that full string, or just use mediawiki
or mediawiki.org.

* `editor-type` - _required_ - If you want to filter by editor-type, use one of anonymous, group-bot (registered
accounts belonging to the bot group), name-bot (registered accounts not belonging to
the bot group but having bot-like names) or user (registered account not in bot group
nor having bot-like name). If you are interested in edits regardless of their
editor-type, use all-editor-types.

    Possible values: all-editor-types, anonymous, group-bot, name-bot, user.
* `page-type` - _required_ - If you want to filter by page-type, use one of content (edits on pages in content
namespaces) or non-content (edits on pages in non-content namespaces). If you are
interested in edits regardless of their page-type, use all-page-types.

    Possible values: all-page-types, content, non-content.
* `year` - _required_ - The year of the date for which to retrieve top editors, in YYYY format.
* `month` - _required_ - The month of the date for which to retrieve top editors, in MM format. If you want to get the top editors of a whole month, the day parameter should be all-days.
* `day` - _required_ - The day of the date for which to retrieve top editors, in DD format, or all-days for a monthly value.

### Get top 100 editors by edits count.

> Given a Mediawiki project and a date (day or month), returns a timeseries of the top<br/>
> 100 editors by edits count. You can filter by editor-type (all-editor-types,<br/>
> anonymous, group-bot, name-bot, user) or page-type (all-page-types, content or<br/>
> non-content). The user_text returned is either the mediawiki user_text if the user is<br/>
> registered, or null if user is anonymous.<br/>
> <br/>
> - Stability: [experimental](https://www.mediawiki.org/wiki/API_versioning#Experimental)<br/>
> - Rate limit: 25 req/s<br/>
> - License: Data accessible via this endpoint is available under the<br/>
>   [CC0 1.0 license](https://creativecommons.org/publicdomain/zero/1.0/).

*Tags:* `Editors data`

#### Input Parameters
* `project` - _required_ - The name of any Wikimedia project formatted like {language code}.{project name},
for example en.wikipedia. You may pass en.wikipedia.org and the .org will be stripped
off. For projects like commons without language codes, use commons.wikimedia. For
projects like www.mediawiki.org, you can use that full string, or just use mediawiki
or mediawiki.org.

* `editor-type` - _required_ - If you want to filter by editor-type, use one of anonymous, group-bot (registered
accounts belonging to the bot group), name-bot (registered accounts not belonging to
the bot group but having bot-like names) or user (registered account not in bot group
nor having bot-like name). If you are interested in edits regardless of their
editor-type, use all-editor-types.

    Possible values: all-editor-types, anonymous, group-bot, name-bot, user.
* `page-type` - _required_ - If you want to filter by page-type, use one of content (edits on pages in content
namespaces) or non-content (edits on pages in non-content namespaces). If you are
interested in edits regardless of their page-type, use all-page-types.

    Possible values: all-page-types, content, non-content.
* `year` - _required_ - The year of the date for which to retrieve top editors, in YYYY format.
* `month` - _required_ - The month of the date for which to retrieve top editors, in MM format. If you want to get the top editors of a whole month, the day parameter should be all-days.
* `day` - _required_ - The day of the date for which to retrieve top editors, in DD format, or all-days for a monthly value.

### Get top 100 editors by net bytes-difference.

> Given a Mediawiki project and a date (day or month), returns a timeseries of the top 100<br/>
> editors by net bytes-difference. You can filter by editor-type (all-editor-types, anonymous,<br/>
> group-bot, name-bot, user) or page-type (all-page-types, content or non-content). The<br/>
> user_text returned is either the mediawiki user_text if the user is registered, or<br/>
> "Anonymous Editor" if user is anonymous.<br/>
> <br/>
> - Stability: [experimental](https://www.mediawiki.org/wiki/API_versioning#Experimental)<br/>
> - Rate limit: 25 req/s<br/>
> - License: Data accessible via this endpoint is available under the<br/>
>   [CC0 1.0 license](https://creativecommons.org/publicdomain/zero/1.0/).

*Tags:* `Editors data`

#### Input Parameters
* `project` - _required_ - The name of any Wikimedia project formatted like {language code}.{project name},
for example en.wikipedia. You may pass en.wikipedia.org and the .org will be stripped
off. For projects like commons without language codes, use commons.wikimedia. For
projects like www.mediawiki.org, you can use that full string, or just use mediawiki
or mediawiki.org.

* `editor-type` - _required_ - If you want to filter by editor-type, use one of anonymous, group-bot (registered
accounts belonging to the bot group), name-bot (registered accounts not belonging to
the bot group but having bot-like names) or user (registered account not in bot group
nor having bot-like name). If you are interested in edits regardless of their
editor-type, use all-editor-types.

    Possible values: all-editor-types, anonymous, group-bot, name-bot, user.
* `page-type` - _required_ - If you want to filter by page-type, use one of content (edits on pages in content
namespaces) or non-content (edits on pages in non-content namespaces). If you are
interested in edits regardless of their page-type, use all-page-types.

    Possible values: all-page-types, content, non-content.
* `year` - _required_ - The year of the date for which to retrieve top editors, in YYYY format.
* `month` - _required_ - The month of the date for which to retrieve top editors, in MM format. If you want to get the top editors of a whole month, the day parameter should be all-days.
* `day` - _required_ - The day of the date for which to retrieve top editors, in DD format, or all-days for a monthly value.

### Get edits counts for a project.

> Given a Mediawiki project and a date range, returns a timeseries of edits counts.<br/>
> You can filter by editors-type (all-editor-types, anonymous, bot, registered) and<br/>
> page-type (all-page-types, content or non-content). You can choose between daily and<br/>
> monthly granularity as well.<br/>
> <br/>
> - Stability: [experimental](https://www.mediawiki.org/wiki/API_versioning#Experimental)<br/>
> - Rate limit: 25 req/s<br/>
> - License: Data accessible via this endpoint is available under the<br/>
>   [CC0 1.0 license](https://creativecommons.org/publicdomain/zero/1.0/).

*Tags:* `Edits data`

#### Input Parameters
* `project` - _required_ - The name of any Wikimedia project formatted like {language code}.{project name},
for example en.wikipedia. You may pass en.wikipedia.org and the .org will be stripped
off.  For projects like commons without language codes, use commons.wikimedia.
For projects like www.mediawiki.org, you can use that full string, or just use
mediawiki or mediawiki.org. If you're interested in the aggregation of
all projects, use all-projects.

* `editor-type` - _required_ - If you want to filter by editor-type, use one of anonymous, group-bot (registered
accounts belonging to the bot group), name-bot (registered accounts not belonging
to the bot group but having bot-like names) or user (registered account not in bot
group nor having bot-like name). If you are interested in edits regardless
of their editor-type, use all-editor-types.

    Possible values: all-editor-types, anonymous, group-bot, name-bot, user.
* `page-type` - _required_ - If you want to filter by page-type, use one of content (edits on pages in content
namespaces) or non-content (edits on pages in non-content namespaces). If you are
interested in edits regardless of their page-type, use all-page-types.

    Possible values: all-page-types, content, non-content.
* `granularity` - _required_ - The time unit for the response data. As of today, supported values are
daily and monthly.

    Possible values: daily, monthly.
* `start` - _required_ - The date of the first day to include, in YYYYMMDD format
* `end` - _required_ - The date of the last day to include, in YYYYMMDD format

### Get edit counts for a page in a project.

> Given a Mediawiki project, a page-title prefixed with its canonical namespace (for<br/>
> instance 'User:Jimbo_Wales') and a date range, returns a timeseries of edit counts.<br/>
> You can filter by editors-type (all-editor-types, anonymous, group-bot, name-bot, user).<br/>
> You can choose between daily and monthly granularity as well.<br/>
> <br/>
> - Stability: [experimental](https://www.mediawiki.org/wiki/API_versioning#Experimental)<br/>
> - Rate limit: 25 req/s<br/>
> - License: Data accessible via this endpoint is available under the<br/>
>   [CC0 1.0 license](https://creativecommons.org/publicdomain/zero/1.0/).

*Tags:* `Edits data`

#### Input Parameters
* `project` - _required_ - The name of any Wikimedia project formatted like {language code}.{project name},
for example en.wikipedia. You may pass en.wikipedia.org and the .org will be stripped
off. For projects like commons without language codes, use commons.wikimedia. For
projects like www.mediawiki.org, you can use that full string, or just use mediawiki
or mediawiki.org.

* `page-title` - _required_ - The page-title to request edits for. It should be prefixed with canonical namespace.
Spaces will be converted to underscores.

* `editor-type` - _required_ - If you want to filter by editor-type, use one of anonymous, group-bot (registered
accounts belonging to the bot group), name-bot (registered accounts not belonging to
the bot group but having bot-like names) or user (registered account not in bot group
nor having bot-like name). If you are interested in edits regardless of their
editor-type, use all-editor-types.

    Possible values: all-editor-types, anonymous, group-bot, name-bot, user.
* `granularity` - _required_ - Time unit for the response data. As of today, supported values are daily and monthly

    Possible values: daily, monthly.
* `start` - _required_ - The date of the first day to include, in YYYYMMDD format
* `end` - _required_ - The date of the last day to include, in YYYYMMDD format

### Given a project and a date range, returns a timeseries of pagecounts.<br/>
> You can filter by access site (mobile or desktop) and you can choose between monthly,<br/>
> daily and hourly granularity as well.<br/>
> <br/>
> - Stability: [experimental](https://www.mediawiki.org/wiki/API_versioning#Experimental)<br/>
> - Rate limit: 100 req/s<br/>
> - License: Data accessible via this endpoint is available under the<br/>
>   [CC0 1.0 license](https://creativecommons.org/publicdomain/zero/1.0/).

*Tags:* `Legacy data`

#### Input Parameters
* `project` - _required_ - The name of any Wikimedia project formatted like {language code}.{project name},
for example en.wikipedia. You may pass en.wikipedia.org and the .org will be stripped
off. For projects like commons without language codes, use commons.wikimedia.

* `access-site` - _required_ - If you want to filter by access site, use one of desktop-site or mobile-site. If you are interested in pagecounts regardless of access site use all-sites.
    Possible values: all-sites, desktop-site, mobile-site.
* `granularity` - _required_ - The time unit for the response data. As of today, the supported granularities for
this endpoint are hourly, daily and monthly.

    Possible values: hourly, daily, monthly.
* `start` - _required_ - The timestamp of the first hour/day/month to include, in YYYYMMDDHH format.
* `end` - _required_ - The timestamp of the last hour/day/month to include, in YYYYMMDDHH format.
In hourly and daily granularities this value is inclusive, in the monthly granularity
this value is exclusive.


### Get pageview counts for a project.

> Given a date range, returns a timeseries of pageview counts. You can filter by project,<br/>
> access method and/or agent type. You can choose between daily and hourly granularity<br/>
> as well.<br/>
> <br/>
> - Stability: [stable](https://www.mediawiki.org/wiki/API_versioning#Stable)<br/>
> - Rate limit: 100 req/s<br/>
> - License: Data accessible via this endpoint is available under the<br/>
>   [CC0 1.0 license](https://creativecommons.org/publicdomain/zero/1.0/).

*Tags:* `Pageviews data`

#### Input Parameters
* `project` - _required_ - If you want to filter by project, use the domain of any Wikimedia project,
for example 'en.wikipedia.org', 'www.mediawiki.org' or 'commons.wikimedia.org'.
If you are interested in all pageviews regardless of project, use all-projects.

* `access` - _required_ - If you want to filter by access method, use one of desktop, mobile-app or mobile-web.
If you are interested in pageviews regardless of access method, use all-access.

    Possible values: all-access, desktop, mobile-app, mobile-web.
* `agent` - _required_ - If you want to filter by agent type, use one of user or spider. If you are interested
in pageviews regardless of agent type, use all-agents.

    Possible values: all-agents, user, spider.
* `granularity` - _required_ - The time unit for the response data. As of today, the supported granularities for this
endpoint are hourly, daily, and monthly.

    Possible values: hourly, daily, monthly.
* `start` - _required_ - The timestamp of the first hour/day/month to include, in YYYYMMDDHH format
* `end` - _required_ - The timestamp of the last hour/day/month to include, in YYYYMMDDHH format

### Get pageview counts for a page.

> Given a Mediawiki article and a date range, returns a daily timeseries of its pageview<br/>
> counts. You can also filter by access method and/or agent type.<br/>
> <br/>
> - Stability: [stable](https://www.mediawiki.org/wiki/API_versioning#Stable)<br/>
> - Rate limit: 100 req/s<br/>
> - License: Data accessible via this endpoint is available under the<br/>
>   [CC0 1.0 license](https://creativecommons.org/publicdomain/zero/1.0/).

*Tags:* `Pageviews data`

#### Input Parameters
* `project` - _required_ - If you want to filter by project, use the domain of any Wikimedia project,
for example 'en.wikipedia.org', 'www.mediawiki.org' or 'commons.wikimedia.org'.

* `access` - _required_ - If you want to filter by access method, use one of desktop, mobile-app
or mobile-web. If you are interested in pageviews regardless of access method,
use all-access.

    Possible values: all-access, desktop, mobile-app, mobile-web.
* `agent` - _required_ - If you want to filter by agent type, use one of user, bot or spider. If you are
interested in pageviews regardless of agent type, use all-agents.

    Possible values: all-agents, user, spider, bot.
* `article` - _required_ - 'The title of any article in the specified project. Any spaces should be replaced
with underscores. It also should be URI-encoded, so that non-URI-safe characters like
%, / or ? are accepted. Example: Are_You_the_One%3F'.

* `granularity` - _required_ - The time unit for the response data. As of today, the only supported granularity for
this endpoint is daily and monthly.

    Possible values: daily, monthly.
* `start` - _required_ - The date of the first day to include, in YYYYMMDD or YYYYMMDDHH format
* `end` - _required_ - The date of the last day to include, in YYYYMMDD or YYYYMMDDHH format

### Get pageviews by country and access method.

> Lists the pageviews to this project, split by country of origin for a given month.<br/>
> Because of privacy reasons, pageviews are given in a bucketed format, and countries<br/>
> with less than 100 views do not get reported.<br/>
> Stability: [experimental](https://www.mediawiki.org/wiki/API_versioning#Experimental)<br/>
> - Rate limit: 100 req/s<br/>
> - License: Data accessible via this endpoint is available under the<br/>
>   [CC0 1.0 license](https://creativecommons.org/publicdomain/zero/1.0/).

*Tags:* `Pageviews data`

#### Input Parameters
* `project` - _required_ - If you want to filter by project, use the domain of any Wikimedia project,
for example 'en.wikipedia.org', 'www.mediawiki.org' or 'commons.wikimedia.org'.

* `access` - _required_ - If you want to filter by access method, use one of desktop, mobile-app or mobile-web.
If you are interested in pageviews regardless of access method, use all-access.

    Possible values: all-access, desktop, mobile-app, mobile-web.
* `year` - _required_ - The year of the date for which to retrieve top countries, in YYYY format.
* `month` - _required_ - The month of the date for which to retrieve top countries, in MM format.


### Get the most viewed articles for a project.

> Lists the 1000 most viewed articles for a given project and timespan (month or day).<br/>
> You can filter by access method.<br/>
> <br/>
> - Stability: [stable](https://www.mediawiki.org/wiki/API_versioning#Stable)<br/>
> - Rate limit: 100 req/s<br/>
> - License: Data accessible via this endpoint is available under the<br/>
>   [CC0 1.0 license](https://creativecommons.org/publicdomain/zero/1.0/).

*Tags:* `Pageviews data`

#### Input Parameters
* `project` - _required_ - If you want to filter by project, use the domain of any Wikimedia project,
for example 'en.wikipedia.org', 'www.mediawiki.org' or 'commons.wikimedia.org'.

* `access` - _required_ - If you want to filter by access method, use one of desktop, mobile-app or mobile-web.
If you are interested in pageviews regardless of access method, use all-access.

    Possible values: all-access, desktop, mobile-app, mobile-web.
* `year` - _required_ - The year of the date for which to retrieve top articles, in YYYY format.
* `month` - _required_ - The month of the date for which to retrieve top articles, in MM format. If you want
to get the top articles of a whole month, the day parameter should be all-days.

* `day` - _required_ - The day of the date for which to retrieve top articles, in DD format.

### Get newly registered users counts for a project.

> Given a Mediawiki project and a date range, returns a timeseries of its newly registered<br/>
> users counts. You can choose between daily and monthly granularity. The newly registered<br/>
> users value is computed with self-created users only, not auto-login created ones.<br/>
> <br/>
> - Stability: [experimental](https://www.mediawiki.org/wiki/API_versioning#Experimental)<br/>
> - Rate limit: 25 req/s<br/>
> - License: Data accessible via this endpoint is available under the<br/>
>   [CC0 1.0 license](https://creativecommons.org/publicdomain/zero/1.0/).

*Tags:* `Registered users data`

#### Input Parameters
* `project` - _required_ - The name of any Wikimedia project formatted like {language code}.{project name},
for example en.wikipedia. You may pass en.wikipedia.org and the .org will be stripped
off.  For projects like commons without language codes, use commons.wikimedia.
For projects like www.mediawiki.org, you can use that full string, or just use
mediawiki or mediawiki.org. If you're interested in the aggregation of
all projects, use all.

* `granularity` - _required_ - The time unit for the response data. As of today, supported values are
daily and monthly.

    Possible values: daily, monthly.
* `start` - _required_ - The date of the first day to include, in YYYYMMDD format
* `end` - _required_ - The date of the last day to include, in YYYYMMDD format

### Get unique devices count per project

> Given a project and a date range, returns a timeseries of unique devices counts.<br/>
> You need to specify a project, and can filter by accessed site (mobile or desktop).<br/>
> You can choose between daily and hourly granularity as well.<br/>
> <br/>
> - Stability: [stable](https://www.mediawiki.org/wiki/API_versioning#Stable)<br/>
> - Rate limit: 100 req/s<br/>
> - License: Data accessible via this endpoint is available under the<br/>
>   [CC0 1.0 license](https://creativecommons.org/publicdomain/zero/1.0/).

*Tags:* `Unique devices data`

#### Input Parameters
* `project` - _required_ - If you want to filter by project, use the domain of any Wikimedia project,
for example 'en.wikipedia.org', 'www.mediawiki.org' or 'commons.wikimedia.org'.

* `access-site` - _required_ - If you want to filter by accessed site, use one of desktop-site or mobile-site.
If you are interested in unique devices regardless of accessed site, use or all-sites.

    Possible values: all-sites, desktop-site, mobile-site.
* `granularity` - _required_ - The time unit for the response data. As of today, the supported granularities
for this endpoint are daily and monthly.

    Possible values: daily, monthly.
* `start` - _required_ - The timestamp of the first day/month to include, in YYYYMMDD format
* `end` - _required_ - The timestamp of the last day/month to include, in YYYYMMDD format

### Machine-translate content

> Fetches the machine translation for the posted content from the source<br/>
> to the destination language.<br/>
> <br/>
> Stability: [unstable](https://www.mediawiki.org/wiki/API_versioning#Unstable)

*Tags:* `Transform`

#### Input Parameters
* `from_lang` - _required_ - The source language code
* `to_lang` - _required_ - The target language code

### Machine-translate content

> Fetches the machine translation for the posted content from the source<br/>
> to the destination language.<br/>
> <br/>
> Stability: [unstable](https://www.mediawiki.org/wiki/API_versioning#Unstable)

*Tags:* `Transform`

#### Input Parameters
* `from_lang` - _required_ - The source language code
* `to_lang` - _required_ - The target language code
* `provider` - _required_ - The machine translation provider id
    Possible values: Apertium, Yandex, Youdao.

### Lists the language pairs supported by the back-end

> Fetches the list of language pairs the back-end service can translate<br/>
> <br/>
> Stability: [unstable](https://www.mediawiki.org/wiki/API_versioning#Unstable)

*Tags:* `Transform`

### Lists the tools available for a language pair

> Fetches the list of tools that are available for the given pair of languages.<br/>
> <br/>
> Stability: [unstable](https://www.mediawiki.org/wiki/API_versioning#Unstable)

*Tags:* `Transform`

#### Input Parameters
* `from` - _required_ - The source language code
* `to` - _required_ - The target language code

### Lists the tools and language pairs available for the given tool category

> Fetches the list of tools and all of the language pairs it can translate<br/>
> <br/>
> Stability: [unstable](https://www.mediawiki.org/wiki/API_versioning#Unstable)

*Tags:* `Transform`

#### Input Parameters
* `tool` - _required_ - The tool category to list tools and language pairs for
    Possible values: mt, dictionary.

### Lists the tools and language pairs available for the given tool category

> Fetches the list of tools and all of the language pairs it can translate<br/>
> <br/>
> Stability: [unstable](https://www.mediawiki.org/wiki/API_versioning#Unstable)

*Tags:* `Transform`

#### Input Parameters
* `tool` - _required_ - The tool category to list tools and language pairs for
    Possible values: mt, dictionary.
* `from` - _required_ - The source language code

### Lists the tools and language pairs available for the given tool category

> Fetches the list of tools and all of the language pairs it can translate<br/>
> <br/>
> Stability: [unstable](https://www.mediawiki.org/wiki/API_versioning#Unstable)

*Tags:* `Transform`

#### Input Parameters
* `tool` - _required_ - The tool category to list tools and language pairs for
    Possible values: mt, dictionary.
* `from` - _required_ - The source language code
* `to` - _required_ - The target language code

### Fetch the dictionary meaning of a word

> Fetches the dictionary meaning of a word from a language and displays<br/>
> it in the target language.<br/>
> <br/>
> Stability: [unstable](https://www.mediawiki.org/wiki/API_versioning#Unstable)

*Tags:* `Transform`

#### Input Parameters
* `from_lang` - _required_ - The source language code
* `to_lang` - _required_ - The target language code
* `word` - _required_ - The word to lookup

### Fetch the dictionary meaning of a word

> Fetches the dictionary meaning of a word from a language and displays<br/>
> it in the target language.<br/>
> <br/>
> Stability: [unstable](https://www.mediawiki.org/wiki/API_versioning#Unstable)

*Tags:* `Transform`

#### Input Parameters
* `from_lang` - _required_ - The source language code
* `to_lang` - _required_ - The target language code
* `word` - _required_ - The word to lookup
* `provider` - _required_ - The dictionary provider id
    Possible values: JsonDict, Dictd.

## License

**flow**ground :- Telekom iPaaS / wikimedia-org-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
