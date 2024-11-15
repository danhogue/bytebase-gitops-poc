# bytebase-gitops-poc



chdump 'clickhouse://default:@localhost:9000/default' > schema_dmp.sql

- The developer creates a Pull Request containing the SQL script;
- SQL Review CI is automatically triggered to review SQL and offers suggestions via a comment in the PR;
- The team leader or another peer on the dev teams approves the change and merges the SQL script into the watched branch (default is the main branch);
- The merge event automatically triggers the rollout pipeline in Bytebase and creates a ticket capturing the intended change;
- (Optional) an approval flow will be auto matched based on the change risk and be followed via Bytebase’s built-in UI;
- Approved scripts are executed gradually according to the configured rollout stages;
- When the rollout is completed, Bitbucket CI may get notified and proceed to deploy the application.
