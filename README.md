# claude code

`curl -fsSL https://claude.ai/install.sh | bash`

## Disk Space

In terminal:

`ollama list`

`df -h /`

`du -sh ~/.ollama/models`

general disk space
`du -h -d 1 ~ | sort -h`

npm cache
`npm cache clean --force`

## Launch claude without pro/max/enterprise key or api

`ollama launch claude --config`
