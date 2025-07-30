# terraform-gcp-github-actions

Automating Terraform Deployment to Google Cloud with GitHub Actions

For details terraforming steps [please refer the blog](https://medium.com/@vikramshinde/automating-terraform-deployment-to-google-cloud-with-github-actions-17516c4fb2e5)

## Updated notes

The workflow file has been updated to use the newer `google-github-actions/auth` GitHub Action with Workload Identity
Federation. No more long living service account keys!

## Security scanning

Added pre-commit hooks and GitHub Actions for shift-left security:

### Pre-commit

```bash
pip install pre-commit
pre-commit install
```

Runs terraform fmt, validate, tflint, tfsec, and secret scanning on each commit.

### GitHub Actions

- `terraform-security.yaml` - Runs tfsec, checkov, and tflint. Results show up in Security tab
- `workflow.yaml` - Handles the actual deployment

## Future reading

GitHub action: <https://github.com/google-github-actions/auth>

GCP documentation for WIF: <https://cloud.google.com/iam/docs/workload-identity-federation>
