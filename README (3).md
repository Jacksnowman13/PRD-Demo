# Conversion warning prototype

A clickable concept prototype for a proposed change to the file upload flow in a data platform. When a user changes a column's type (say, string to double) and some values can't be converted, today those values quietly become NULL. This prototype shows the proposed fix:

- **Non-blocking alert** that says how many values failed and whether any of them were visible in the 50-row preview
- **Failure behavior setting**: default to NULL, or throw an error like a direct `CAST` does elsewhere
- **Side-by-side review** of the affected rows, with a one-click revert

Use the **Proposed flow / Today's flow** toggle at the top to compare the two.

The sample file is synthetic: 1,000 rows, with 62 messy `revenue` values (`pending`, `-`, `N/A`, `$1,231.62`, `1,196.26`, `TBD`) all placed after row 50, so the preview looks clean.

Everything is in `index.html` with no dependencies, and nothing leaves the browser. Not affiliated with or endorsed by Databricks.
