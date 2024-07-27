# Documentation website for the Systematic Trading Toolkit (STTK)

## Requirements

Be sure to have the poetry virtual environment activated:
```zsh
poetry shell
```
Then install the necessary dependencies:
```zsh
poetry install
```

## Development

To run the live preview server of MkDocs, `cd` into the `website/` directory and run:
```zsh
mkdocs serve
```


## Deployment

To deploy the website, run:
```zsh
mkdocs gh-deploy
```