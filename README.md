## Extract a key–value pair by index from JSON to fields in n8n

This workflow template takes a JSON object and a row index and returns exactly one key–value pair at that index. It is useful when you need to pick a single entry from structured JSON data and pass it to downstream nodes in n8n.

---

## Who’s it for

- Developers working with API responses
- Makers building quick automations
- Analysts extracting specific values from JSON
- Anyone needing lightweight JSON manipulation without complex logic

---

## How it works

1. **Manual Trigger** starts the workflow.
2. **Set – Input JSON** node contains:
   - `myData`: JSON object with key–value pairs
   - `rowIndex`: zero‑based index of the pair to extract
3. **Code (Python)** node iterates through the object and selects the key–value pair at the specified index.
4. **Set – Key** node outputs the extracted key.
5. **Set – Value** node outputs the extracted value.
6. The extracted key and value are available for further processing.

---

## How to set up

1. Import the workflow into your n8n instance.
2. Open the **Input JSON** node and replace the sample JSON:

```json
{
  "myData": {
    "name": "Alice",
    "age": "30",
    "city": "Paris"
  },
  "rowIndex": "1"
}
```

3. Click **Execute workflow**.
4. Check the output of the **Key** and **Value** nodes.

---

## Requirements

- n8n (cloud or self‑hosted)
- Code node enabled (Python)
- Valid JSON object as input
- Zero‑based integer index (`rowIndex`)

---

## How to customize

- **Pick by key instead of index**: Modify the Code node to directly reference a key name.
- **Nested JSON support**: Add logic to flatten or traverse nested objects.
- **Output format**: Return a combined object `{ key, value }` instead of separate fields.
- **Validation**: Add guards for missing keys or invalid index values.

---

## Add-ons

- Replace Manual Trigger with **Webhook** to accept live JSON payloads.
- Log extracted values into Google Sheets or a database.
- Add conditional routing based on extracted key or value.
- Chain with transformation workflows.

---

## Use Case Examples

- Extract a specific field from an API response.
- Pick one answer from a form submission.
- Read configuration values dynamically.
- Control workflow routing using extracted JSON data.

---

## Common troubleshooting

| Issue                 | Possible Cause               | Solution                       |
| --------------------- | ---------------------------- | ------------------------------ |
| Index out of range    | Invalid `rowIndex`           | Ensure index is within bounds  |
| Wrong value extracted | JSON key order differs       | Use key‑based selection        |
| Empty output          | `myData` is empty or invalid | Validate JSON input            |
| Code node error       | Python disabled              | Enable Python or convert to JS |
| Unexpected type       | Non‑string value             | Cast value before use          |

---

## Need Help?

If you need:

- Key‑based extraction
- Nested JSON handling
- Webhook‑based input
- Advanced validation or logging

Contact **WeblineIndia** for workflow customization and support.
