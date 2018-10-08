# Fixtures & management commands

To manage some data we use fixtures & custom commands. Mostly custom commands are used for managing email templates and for updating permissions, because their definitions are complex and hard to control using fixtures.

* `python manage.py update_notifications` - _update email templates_
* `python manage.py update_action_points_permissions`  - _update module related permissions_

All commands are designed to be safely executed multiple times without data duplication, so they are recommended to run after every deployment to be sure that actual data will be provided.

