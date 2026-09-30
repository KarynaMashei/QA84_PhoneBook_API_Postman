# PhoneBook API Tests with Postman CLI

Training project developed during the QA Automation Engineer program at AIT Technology School. It demonstrates automated API test execution for the PhoneBook backend with Postman CLI and GitHub Actions.

![Postman API tests](https://github.com/KarynaMashei/QA84_PhoneBook_API_Postman/actions/workflows/main.yml/badge.svg)

## Technology stack

- Postman collections and environments
- Postman CLI
- GitHub Actions
- repository secrets for API-key authentication

## Automated workflow

The workflow in `.github/workflows/main.yml` runs on every push and:

1. checks out the repository;
2. installs Postman CLI on a Windows runner;
3. authenticates with the `POSTMAN_API_KEY` repository secret;
4. runs the configured PhoneBook API collection and environment;
5. supplies the backend base URL as an environment variable.

## Run from Postman CLI

The collection and environment are referenced by their Postman workspace IDs. A valid Postman API key with access to that workspace is required.

```bash
postman login --with-api-key <POSTMAN_API_KEY>
postman collection run <COLLECTION_ID> -e <ENVIRONMENT_ID> --env-var "BaseURI=<BACKEND_URL>"
```

## Notes

This is a training project, not a production or client application. Exported collection and environment JSON files are not currently included in the repository; the GitHub Actions workflow uses the versions stored in the Postman workspace.
