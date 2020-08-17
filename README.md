# Node Lambdas

![Node Lambdas](https://avatars0.githubusercontent.com/u/69599650?s=100&v=4)

## What is this?

Just a tiny JS program that pipes the input/output of your CLI commands to a cloud microservice via HTTPS.

```
            input
              v
  https://[function-name].jsfn.run/[arguments]
              v
            output
```

Think of YAML, for example.
You have a JSON and you want to convert it to YAML from your CLI.

So you read your JSON file with `cat`, pipe it to the `yaml` command and get the output back in the command line.

But oh wait, there's no `yaml` program in your computer!

Well, you could install some package in your machine... or you can pipe your data directly to a publicly available `yaml` command online!

## Why

Quite often we need to do simple tasks like formatting a JSON file or decoding a base64 string.
Usually we either install some package or go to a website dedicated to that.

But what if you need that in an automation script?

## Using with cURL

```bash
cat your.json | curl -X POST https://yaml.jsfn.run --data @-
```

## Using the `fn` cli

Start by installing the module globally:

```
npm i -g @node-lambdas/cli
```

Make sure `fn` can be reached from your shell. If not, you should check your `$PATH` to see if your global npm folder is added there.
To check, just run `fn`.

Now you can use the CLI to invoke any of the available microservices.

### Examples

```bash

# convert JSON to YAML
cat your.json | fn yaml

# calculate the sha256 hash for the content of file.txt
cat file.txt | fn sha 256

# convert Markdown to HTML
cat README.md | fn markdown

```

## Available Node.js micro services

Missing something here? You can also [request a new service](https://docs.google.com/forms/d/e/1FAIpQLSdH38n0y65NZyAc3oj_T6KQhYtlt3BruvZq21BzPkiMVYtl5w/viewform?usp=sf_link).

- [base64](https://base64.jsfn.run)
- [format-json](https://format-json.jsfn.run)
- [markdown](https://markdown.jsfn.run)
- [md5](https://md5.jsfn.run)
- [sha](https://sha.jsfn.run)
- [yaml](https://yaml.jsfn.run)
- [random](https://random.jsfn.run)
