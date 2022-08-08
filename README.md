# Contributing to the Knowledge Base

This is the repository for adding Knowledge Base content to the NIH CFDE Portal. To add your data:

1. Clone this repository.
2. Add Markdown content to the folder named after your Common Fund group.
3. Create a Pull Request to this repository. This will make your annotations accessible to the content generation team.

The content registry team will review your annotations and handle the workflow to add content to the portal website.

### Have questions?

Ask in the #content-generation-sprint slack channel or create an issue.

### Knowledge Base Final Product Options

The final product of this process is a chunk of rendered web content attached to a controlled vocabulary ID. For example: https://app.nih-cfde.org/chaise/record/#1/CFDE:gene/nid=1

The options for Markdown chunks on this page are:

- A table of links to pages describing this gene (no iframe)
- A widget displaying GTEx expression data (via iframe)
- A widget showing GTEx transcriptional activity (via iframe)
- A widget showing the UCSC Genome Browser (via iframe)

### Markdown Formatting with ERMrestjs

The Markdown language used to create the registry is ERMrestjs. This is similar to GitHub Markdown, but is more restricted.  This language supports direct rendering of content, like the alias table listed above, or the inclusion of content from external sources using an iframe.

The reference for this language is here: https://github.com/informatics-isi-edu/ermrestjs/blob/master/docs/user-docs/markdown-formatting.md

### Working with the CFDE to Deposit Content

The CFDE-CC will manage:

1. Integration and aggregation of various independent Markdown chunks for each object/ID
2. Actual uploads to the portal database

Content creators have several options for what to provide.

#### JSON Container with a List of Objects

A JSON container needs to have: a list of objects by ID and a chunk of Markdown for each ID.

An example from an iframe container for anatomy terms is below. The `resource_markdown` field using ERMrestjs formatting.

```
[
    {"id": "UBERON:0000167", "resource_markdown": "::: iframe [**Expression data from GTEx:**](https://mii.podvis.org/cfde-ge1/#/anatomy?uberon_ids=UBERON%3A0000167&width=1400&height=550&numTopGenes=25){width=\"1400\" height=\"550\" style=\"border: 1px solid black;\" caption-style=\"font-size: 24px;\" caption-link=\"https://gtexportal.org/home/api-docs/index.html#/expression\" caption-target=\"_blank\"} \n:::\n\n"},
    {"id": "UBERON:0000178", "resource_markdown": "::: iframe [**Expression data from GTEx:**](https://mii.podvis.org/cfde-ge1/#/anatomy?uberon_ids=UBERON%3A0000178&width=1400&height=550&numTopGenes=25){width=\"1400\" height=\"550\" style=\"border: 1px solid black;\" caption-style=\"font-size: 24px;\" caption-link=\"https://gtexportal.org/home/api-docs/index.html#/expression\" caption-target=\"_blank\"} \n:::\n\n"},
    {"id": "UBERON:0000363", "resource_markdown": "::: iframe [**Expression data from GTEx:**](https://mii.podvis.org/cfde-ge1/#/anatomy?uberon_ids=UBERON%3A0000363&width=1400&height=550&numTopGenes=25){width=\"1400\" height=\"550\" style=\"border: 1px solid black;\" caption-style=\"font-size: 24px;\" caption-link=\"https://gtexportal.org/home/api-docs/index.html#/expression\" caption-target=\"_blank\"} \n:::\n\n"},
    {"id": "UBERON:0000467", "resource_markdown": "::: iframe [**Expression data from GTEx:**](https://mii.podvis.org/cfde-ge1/#/anatomy?uberon_ids=UBERON%3A0000467&width=1400&height=550&numTopGenes=25){width=\"1400\" height=\"550\" style=\"border: 1px solid black;\" caption-style=\"font-size: 24px;\" caption-link=\"https://gtexportal.org/home/api-docs/index.html#/expression\" caption-target=\"_blank\"} \n:::\n\n"},
    {"id": "UBERON:0000955", "resource_markdown": "::: iframe [**Expression data from GTEx:**](https://mii.podvis.org/cfde-ge1/#/anatomy?uberon_ids=UBERON%3A0000955&width=1400&height=550&numTopGenes=25){width=\"1400\" height=\"550\" style=\"border: 1px solid black;\" caption-style=\"font-size: 24px;\" caption-link=\"https://gtexportal.org/home/api-docs/index.html#/expression\" caption-target=\"_blank\"} \n:::\n\n"},
    {"id": "UBERON:0000995", "resource_markdown": "::: iframe [**Expression data from GTEx:**](https://mii.podvis.org/cfde-ge1/#/anatomy?uberon_ids=UBERON%3A0000995&width=1400&height=550&numTopGenes=25){width=\"1400\" height=\"550\" style=\"border: 1px solid black;\" caption-style=\"font-size: 24px;\" caption-link=\"https://gtexportal.org/home/api-docs/index.html#/expression\" caption-target=\"_blank\"} \n:::\n\n"},
    {"id": "UBERON:0000998", "resource_markdown": "::: iframe [**Expression data from GTEx:**](https://mii.podvis.org/cfde-ge1/#/anatomy?uberon_ids=UBERON%3A0000998&width=1400&height=550&numTopGenes=25){width=\"1400\" height=\"550\" style=\"border: 1px solid black;\" caption-style=\"font-size: 24px;\" caption-link=\"https://gtexportal.org/home/api-docs/index.html#/expression\" caption-target=\"_blank\"} \n:::\n\n"},
    {"id": "UBERON:0001008", "resource_markdown": "::: iframe [**Expression data from GTEx:**](https://mii.podvis.org/cfde-ge1/#/anatomy?uberon_ids=UBERON%3A0001008&width=1400&height=550&numTopGenes=25){width=\"1400\" height=\"550\" style=\"border: 1px solid black;\" caption-style=\"font-size: 24px;\" caption-link=\"https://gtexportal.org/home/api-docs/index.html#/expression\" caption-target=\"_blank\"} \n:::\n\n"},
    {"id": "UBERON:0001017", "resource_markdown": "::: iframe [**Expression data from GTEx:**](https://mii.podvis.org/cfde-ge1/#/anatomy?uberon_ids=UBERON%3A0001017&width=1400&height=550&numTopGenes=25){width=\"1400\" height=\"550\" style=\"border: 1px solid black;\" caption-style=\"font-size: 24px;\" caption-link=\"https://gtexportal.org/home/api-docs/index.html#/expression\" caption-target=\"_blank\"} \n:::\n\n"},
    {"id": "UBERON:0002369", "resource_markdown": "::: iframe [**Expression data from GTEx:**](https://mii.podvis.org/cfde-ge1/#/anatomy?uberon_ids=UBERON%3A0002369&width=1400&height=550&numTopGenes=25){width=\"1400\" height=\"550\" style=\"border: 1px solid black;\" caption-style=\"font-size: 24px;\" caption-link=\"https://gtexportal.org/home/api-docs/index.html#/expression\" caption-target=\"_blank\"} \n:::\n\n"}
]
```

Name the JSON file according to the controlled vocabulary it references: gene.json or compound.json.

After creating this file, create a pull request with this repository and drop it off in the folder from your Common Fund group. The CFDE-CC will take care of integration with other markdown and downstream publishing.

#### Providing a list of IDs and Content

You can also provide a list of controlled vocabulary IDs and the content you would like attached. The CFDE-CC can format this into JSON and Markdown, but this process will take longer.
