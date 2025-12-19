## Secret Scope in Databricks Code

```python
from databricks.sdk import WorkspaceClient

w = WorkspaceClient()
w.secrets.put_secret(
    scope="scope_name",
    key="AIS_KEY",
    string_value="key"
)

dbutils.secrets.get(scope="myManagedSecrets", key="AIS_KEY")
```
