# Web-service to aggregate data

This assignment explores the development _and_ unit-test of a web-service, which in-turn depends on other web-services.

## Monitoring the Most Recent

Given a set of Git repo-URLs, the task is to present the date on which each of them was last updated.
The results need to be sorted, starting with the most recent first.

Example: 
```gherkin
Given the Git repo-URLs https://api.github.com/repos/numocityadmin/ocpi-probe, https://api.github.com/repos/ocpi/ocpi
And your server is running on localhost, port 8080,
When a GET request is made on http://localhost:8080
Then your server responds with a sequence of repos and their update-dates:
 ocpi/ocpi 2021-11-17
 numocityadmin/ocpi-probe 2021-08-31
```

## Use of GitHub APIs

Configure the list of GitHub API URLs on the server. It must be possible to add more URLs without altering the code.

When a user makes a GET request on your server, it makes GET requests on the configured github API end-points.
It extracts the `updated_at` property from the json response.

## Choice of output formats

You can choose your output format. E.g., it could be in json, csv or html.

## Tests

Write unit-tests, so that we don't need to manually test the server every time we make a change.

Make sure to cover the following error cases:
- A typo in the configured repository URL
- Error response from github.com
