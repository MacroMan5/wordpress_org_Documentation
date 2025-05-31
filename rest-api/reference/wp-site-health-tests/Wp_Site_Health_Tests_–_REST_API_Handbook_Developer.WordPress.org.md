# Wp Site Health Tests – REST API Handbook | Developer.WordPress.org

**Source URL:** [https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/](https://developer.wordpress.org/rest-api/reference/wp-site-health-tests/)  
**Last Updated:** 2025-05-23T01:13:13.625Z  
**Extracted:** 2025-05-31 16:56:23

---

# Wp Site Health Tests – REST API Handbook

## [Schema](#schema)

The schema defines all the fields that exist within a wp site health test record. Any response from these endpoints can be expected to contain the fields below unless the \`\_filter\` query parameter is used or the schema field only appears in a specific context.

|     |     |
| --- | --- |
| `test` | The name of the test being run.<br><br>JSON data type: string<br><br>Read only<br><br>Context: |
| `label` | A label describing the test.<br><br>JSON data type: string<br><br>Read only<br><br>Context: |
| `status` | The status of the test.<br><br>JSON data type: string<br><br>Read only<br><br>Context:<br><br>One of: `good`, `recommended`, `critical` |
| `badge` | The category this test is grouped in.<br><br>JSON data type: object<br><br>Read only<br><br>Context: |
| `description` | A more descriptive explanation of what the test looks for, and why it is important for the user.<br><br>JSON data type: string<br><br>Read only<br><br>Context: |
| `actions` | HTML containing an action to direct the user to where they can resolve the issue.<br><br>JSON data type: string<br><br>Read only<br><br>Context: |

## [Retrieve a Wp Site Health Test](#retrieve-a-wp-site-health-test)

### [Definition & Example Request](#definition-example-request)

`GET /wp-site-health/v1/tests/background-updates`

Query this endpoint to retrieve a specific wp site health test record.

`$ curl https://example.com/wp-json/wp-site-health/v1/tests/background-updates`

There are no arguments for this endpoint.

## [Retrieve a Wp Site Health Test](#retrieve-a-wp-site-health-test-2)

### [Definition & Example Request](#definition-example-request-2)

`GET /wp-site-health/v1/tests/loopback-requests`

Query this endpoint to retrieve a specific wp site health test record.

`$ curl https://example.com/wp-json/wp-site-health/v1/tests/loopback-requests`

There are no arguments for this endpoint.

## [Retrieve a Wp Site Health Test](#retrieve-a-wp-site-health-test-3)

### [Definition & Example Request](#definition-example-request-3)

`GET /wp-site-health/v1/tests/https-status`

Query this endpoint to retrieve a specific wp site health test record.

`$ curl https://example.com/wp-json/wp-site-health/v1/tests/https-status`

There are no arguments for this endpoint.

## [Retrieve a Wp Site Health Test](#retrieve-a-wp-site-health-test-4)

### [Definition & Example Request](#definition-example-request-4)

`GET /wp-site-health/v1/tests/dotorg-communication`

Query this endpoint to retrieve a specific wp site health test record.

`$ curl https://example.com/wp-json/wp-site-health/v1/tests/dotorg-communication`

There are no arguments for this endpoint.

## [Retrieve a Wp Site Health Test](#retrieve-a-wp-site-health-test-5)

### [Definition & Example Request](#definition-example-request-5)

`GET /wp-site-health/v1/tests/authorization-header`

Query this endpoint to retrieve a specific wp site health test record.

`$ curl https://example.com/wp-json/wp-site-health/v1/tests/authorization-header`

There are no arguments for this endpoint.

---

*This documentation was extracted from the database for URLs containing 'wordpress.org'*
