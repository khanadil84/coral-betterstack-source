# Better Stack Coral Source

Coral SQL source for Better Stack uptime monitoring and observability.

## Tables

### betterstack.monitors

Returns Better Stack monitors and status information.

## Example

```sql
SELECT
  attributes__pronounceable_name,
  attributes__status
FROM betterstack.monitors;
```
