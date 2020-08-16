## CLI

Using the CLI simplifies the work of calling different services from command line.

Start by installing the module globally:

```
npm i -g @node-lambdas/cli
```

Then you can use the `fn` binary to execute any of the available services listed below.

**Examples:**

```bash
# convert JSON to YAML
cat your.json | fn yaml

# calculate the sha256 hash for the content of file.txt
cat file.txt | fn sha 256

# convert Markdown to HTML
cat README.md | fn markdown
```

## Node.js micro services
