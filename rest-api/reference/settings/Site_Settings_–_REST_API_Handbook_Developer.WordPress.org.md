# Site Settings – REST API Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/rest-api/reference/settings/](https://developer.wordpress.org/rest-api/reference/settings/)  
**Last Updated:** 2025-05-23T01:01:55.542Z  
**Extracted:** 2025-05-31 16:56:23

---

# Site Settings – REST API Handbook

## [Schema](#schema)

The schema defines all the fields that exist within a Site Setting record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `title` | Site title.<br><br>JSON data type: string<br><br>Context: |
| `description` | Site tagline.<br><br>JSON data type: string<br><br>Context: |
| `url` | Site URL.<br><br>JSON data type: string,  <br>Format: uri<br><br>Context: |
| `email` | This address is used for admin purposes, like new user notification.<br><br>JSON data type: string,  <br>Format: email<br><br>Context: |
| `timezone` | A city in the same timezone as you.<br><br>JSON data type: string<br><br>Context: |
| `date_format` | A date format for all date strings.<br><br>JSON data type: string<br><br>Context: |
| `time_format` | A time format for all time strings.<br><br>JSON data type: string<br><br>Context: |
| `start_of_week` | A day number of the week that the week should start on.<br><br>JSON data type: integer<br><br>Context: |
| `language` | WordPress locale code.<br><br>JSON data type: string<br><br>Context: |
| `use_smilies` | Convert emoticons like :-) and :-P to graphics on display.<br><br>JSON data type: boolean<br><br>Context: |
| `default_category` | Default post category.<br><br>JSON data type: integer<br><br>Context: |
| `default_post_format` | Default post format.<br><br>JSON data type: string<br><br>Context: |
| `posts_per_page` | Blog pages show at most.<br><br>JSON data type: integer<br><br>Context: |
| `show_on_front` | What to show on the front page<br><br>JSON data type: string<br><br>Context: |
| `page_on_front` | The ID of the page that should be displayed on the front page<br><br>JSON data type: integer<br><br>Context: |
| `page_for_posts` | The ID of the page that should display the latest posts<br><br>JSON data type: integer<br><br>Context: |
| `default_ping_status` | Allow link notifications from other blogs (pingbacks and trackbacks) on new articles.<br><br>JSON data type: string<br><br>Context:<br><br>One of: `open`, `closed` |
| `default_comment_status` | Allow people to submit comments on new posts.<br><br>JSON data type: string<br><br>Context:<br><br>One of: `open`, `closed` |
| `site_logo` | Site logo.<br><br>JSON data type: integer<br><br>Context: |
| `site_icon` | Site icon.<br><br>JSON data type: integer<br><br>Context: |

## [Retrieve a Site Setting](#retrieve-a-site-setting)

### [Definition & Example Request](#definition-example-request)

`GET /wp/v2/settings`

Query this endpoint to retrieve a specific Site Setting record.

`$ curl https://example.com/wp-json/wp/v2/settings`

There are no arguments for this endpoint.

## [Update a Site Setting](#update-a-site-setting)

### [Arguments](#arguments)

|     |     |
| --- | --- |
| `[title](#schema-title)` | Site title. |
| `[description](#schema-description)` | Site tagline. |
| `[url](#schema-url)` | Site URL. |
| `[email](#schema-email)` | This address is used for admin purposes, like new user notification. |
| `[timezone](#schema-timezone)` | A city in the same timezone as you. |
| `[date_format](#schema-date_format)` | A date format for all date strings. |
| `[time_format](#schema-time_format)` | A time format for all time strings. |
| `[start_of_week](#schema-start_of_week)` | A day number of the week that the week should start on. |
| `[language](#schema-language)` | WordPress locale code. |
| `[use_smilies](#schema-use_smilies)` | Convert emoticons like :-) and :-P to graphics on display. |
| `[default_category](#schema-default_category)` | Default post category. |
| `[default_post_format](#schema-default_post_format)` | Default post format. |
| `[posts_per_page](#schema-posts_per_page)` | Blog pages show at most. |
| `[show_on_front](#schema-show_on_front)` | What to show on the front page |
| `[page_on_front](#schema-page_on_front)` | The ID of the page that should be displayed on the front page |
| `[page_for_posts](#schema-page_for_posts)` | The ID of the page that should display the latest posts |
| `[default_ping_status](#schema-default_ping_status)` | Allow link notifications from other blogs (pingbacks and trackbacks) on new articles.  <br>One of: `open`, `closed` |
| `[default_comment_status](#schema-default_comment_status)` | Allow people to submit comments on new posts.  <br>One of: `open`, `closed` |
| `[site_logo](#schema-site_logo)` | Site logo. |
| `[site_icon](#schema-site_icon)` | Site icon. |

### [Definition](#definition)

`POST /wp/v2/settings`

### [Example Request](#example-request)

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
