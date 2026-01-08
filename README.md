# Jira REST API in Power Query

This Power Query (M) function loads Jira issues via the Jira REST API and automatically handles pagination.

## Requirements

* Jira REST API access
* Valid Jira API user and API token

The following parameters must be defined externally:
* `JiraApiUrl`
* `JiraApiUser`
* `JiraApiToken`

## Usage

1. Create a new query in Power Query and paste the function code from `load_issues.pq`
2. Call the function by passing a query record:

```m
= JIRA([
    jql = "(project = PROJECT AND created >= 2025-01-01)",
    fields = "summary,status,assignee,created,updated"
])
```

## Notes

* The parameter is a record containing Jira API query options
* Pagination is handled automatically
* The result is returned as a flat table with expanded fields
