# page-agent-skills

Public skills tree for the [Page Agent Chrome Extension](https://github.com/kramar-alexandr/page-agent-ext).

A **skill** is a pre-defined AI automation task for a specific website. The extension fetches skills from this repository and shows them in the side panel for one-click execution.

## Structure

```
skills/
├── index.json              ← Site registry
├── github.com/
│   └── skills.json
├── gmail.google.com/
│   └── skills.json
└── your-site.com/
    └── skills.json
```

## Skill Format

```json
{
  "site": "example.com",
  "version": "1.0.0",
  "skills": [
    {
      "id": "unique-skill-id",
      "name": "Human Readable Name",
      "description": "What this skill does",
      "task": "Natural language instruction for the agent. Use ${paramName} for parameters.",
      "params": [
        {
          "name": "paramName",
          "type": "string",
          "label": "Label shown in UI",
          "multiline": false,
          "required": true
        }
      ],
      "category": "category-name"
    }
  ]
}
```

## Adding Skills for a New Site

1. Create a folder: `skills/your-site.com/`
2. Add `skills.json` following the format above
3. Register the site in `skills/index.json`
4. Open a Pull Request

## Contributing

PRs are welcome! Please follow the format above and test your skills before submitting.
