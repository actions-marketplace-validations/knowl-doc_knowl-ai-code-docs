# knowl-ai-code-docs
Action to generate code documentation for the entire repository with Knowl AI. Increase your and your team's productivity by using high-quality, trusted documents that support your code.

Languages Supported Node.js, javascript, typescript.js, python, java. More on the way...

## How to Generate Docs

- Add the `KNOWL_API_KEY` (generated as above) or create a new one in your repository variables.
- Add the `OPENAI_API_KEY` in your repository variables.
- Run the action manually

#### YAML for the Action
```yaml
name: Generate Code Documents
run-name: Generate Code Documents
on: [workflow_dispatch]

jobs:
  gen-ai-doc:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
        with:
          fetch-depth: 0
      - name: Generate AI docs
        uses: knowl-doc/code-to-doc-manual@main
        env:
          KNOWL_API_KEY: ${{secrets.KNOWL_API_KEY}}
          OPENAI_API_KEY: ${{secrets.OPENAI_API_KEY}}
          OPENAI_BATCH_SIZE: 25
      - name: Upload artifact
        uses: actions/upload-artifact@v2
        with:
          name: knowl_results
          path: knowl_results
```
## Enjoy Code Documents in Your Code Editor
The team can reap all the benefits of well-crafted documents without spending additional time writing them.

- Access information in VS Code using this official plugin
- Generate code documents for the entire repo with CI/CD pipeline integration
- Enjoy consistent, complete, and continuously updated documents
- Add additional information as needed in the AI-powered Rich Text Editor

## Access Documents in VS Code Editor

- Install [Knowl's Official VS Code Plugin](https://marketplace.visualstudio.com/items?itemName=knowl.knowl)
- Extension Settings
  - *Knowl API Key*: Generate and copy the Knowl API Key by navigating to your profile section in the [Knowl](https://app.knowl.io).
  - *Base Git Branch*: Input the name of your base git branch. This could be 'master' or 'main', depending on your repository setup.
#### Example 
This is the example to see the document for an open source project in VS Code 
- Install VS Code Plugin
- Extension Settings
  - Knowl API Key - '4wUXXmv6.QXviMhzcfmOy56rW3NgWu3sT4DyE7R2v'
  - Base Git Branch - 'main'
- To see documents for typescript.js, javascript, and node.js
  - Clone the [Knowl's Fork](https://github.com/knowl-doc/mermaid) of the open-source project mermaid
  -  Open the mermaid folder in VS code
  -  Open any file i.e. mermaid.ts
  -  Click the Knowl icon near any function
  - Login to Knowl page and see the documentation
    - email - demo@example.com
    - password - abc123$%
   
<img src="https://releases.knowl.io/github-action/vs-code-knowl-open.jpg" width="700">

## Access Documents in Knowl Editor
This is the example to see document for an open source project in Knowl Editor
- Login to [Knowl](https://app.knowl.io)
  - reach out to support@knowl.io if you need any help
- Navigate to your repo folder. The folder structure is the same as code repo
- See documents linked to the functions with function, file, folder, and repo level summary

#### Example 
- Login to app.knowl.io
- See the [documentation for mermaid](https://app.knowl.io/k/af8800c3-8ed7-4c10-af62-6e33a054f36d) in Knowl
  - This is the documentation for node.js
  - mermaid.js is an open-source project. Link to [Knowl's Fork](https://github.com/knowl-doc/mermaid)
- See the [documentation for Calculator](https://app.knowl.io/k/2e7f3bd2-54e7-4cc2-ab11-05534d6165bd) in Knowl
  - This is the documentation for Java
  - Calculator is an open-source project. Link to [Knowl's Fork](https://github.com/knowl-doc/Calculator-1)

_screenshot for code-doc snippet linked to a function_

<img src="https://releases.knowl.io/github-action/code-doc.jpg" width="700">
