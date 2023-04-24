# Experiments with Mermaid diagrams

Github Enterprise 3.7 supports Mermaid diagrams, see [Creating Diagrams](https://docs.github.com/en/enterprise-server@3.7/get-started/writing-on-github/working-with-advanced-formatting/creating-diagrams).

Use the [Markdown Preview Mermaid Support](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-mermaid) VS Code extension for creating these diagrams.

## Example

Here is a simple flow chart:

```mermaid
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```
