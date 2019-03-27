# deprovision_inactive

A small node script which uses the Asana API to remove external users (ie without a company email) from an organization if they haven't logged in for set number of days.

## To Run
*   Install node
*   Clone this repository
*   Run `npm install`

### Prerequisites

*   Create a [service account](https://asana.com/guide/help/premium/service-accounts) in the organization (preferred, an admin PAT will also work)
*   Export a csv of Organization Members from the [Organization settings panel](https://asana.com/guide/help/premium/admins#gl-console) or – if you are an Asana eng – obtain a signed url for csv export of the members of the domain.

### Running

You can run the script by setting all required options:

Dry run (displays which users would be deprovisioned):

```
node depro-inactive.js --auth <service account token> --csv <csv export url or file path> --organization_id <organization id> --threshold <# of inactive days>
```

Actually deprovision those users:

```
node depro-inactive.js --auth <service account token> --csv <csv export url or file path> --organization_id <organization id> --threshold <# of inactive days> --mode action
```
