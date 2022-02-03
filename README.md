# Terraform module creator

This is designed to automatically create terraform config files from a text list seperated by new lines of services to enable in GCP

To get the file run:
```bash
gcloud services list --available --project <project>> --format="csv(NAME,TITLE)" 
```

You will need to remove the non `googleapis.com` ones and then remove the `.googleapis.com` suffix from each one, as well as the title.

We still pull in the title as some are named stupidly but still are required.

Once done, run the playbook

```bash
ansible-playbook loop.yml
```

Done