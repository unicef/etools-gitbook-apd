# Integration with permissions framework

APD is tightly connected with permissions framework. Special management command were written to update them. It can be called as

```text
python manage.py update_action_points_permissions
```

and every time when called it collects required set of permissions, removes old permissions which are related to APs \(their targets are starting with `action_points.`\) and creates everything that needed.

This command is very similar to the same in TPM module. For more info see related documentation:

{% embed url="https://razortheory.gitbook.io/third-party-monitoring-module-documentation/technical-documentation/permissions-framework" %}



