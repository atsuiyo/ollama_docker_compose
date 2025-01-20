<div style="display: flex; justify-content: center;">
    <img src="img/doc/ollama.png" alt="alt text" width="200" height="200"> 
    <img src="img/doc/compose.png" alt="alt text" width="200" height="200">
</div>

# This project is for controlling [Ollama](https://github.com/ollama/ollama) in a docker compose environment

- [Run container](#run-container)
- [Remove container](#remove-container)
- [Add model](#add-model)
- [Remove model](#remove-model)

## Usage
Bind models to local folder

### Run container
To run the container, execute the following command:

```bash
docker compose up -d 
```

### Remove container

To use docker's volume feature, use the following command:
```bash
docker compose -f docker-compose-volume.yaml up
```

To remove the container, use the following command:
```bash
docker compose down -d 
```

When using volumes, volumes remain, so you can use the following to remove including volumes

* Warning: Models stored in volumes will be removed
```bash
# docker compose -f docker-compose-volume.yaml down --volume
```

## Add model
Download models using docker compose command

You can use existing ollama commands as they are

### Install llama3.2:1b model
```bash
docker compose exec server ollama run llama3.2:1b
```

## Remove model

### Remove llama3.2:1b model
```bash
docker compose exec server ollama rm llama3.2:1b
```
