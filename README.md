# Magnet On Premise

Basic usage instructions:

```
git clone https://github.com/toolkit-ai/magnet-onpremise.git
./magnet-onpremise/run
```

Follow the prompts, which will generate a file `./magnet-settings.json` that can be edited later.

Wait for the your repo to be downloaded and indexed, which could take some time depending on the size of your repo.

Wait for log output that indicates the server is listening:

```
{"level":30,"time":1714605969796,"pid":104,"hostname":"7b279a1c7d6d","msg":"Server listening at http://0.0.0.0:4000"}
```

Now you can send requests to the locally running server. A basic chat request would look like this:

```
curl -v -X POST http://localhost:4000/chat?noStream=1 \
  -H "Content-Type: application/json" \
  -d '{"prompt": "Explain how dependency injection is implemented in the Utilities class."}'
```

## Options

Run with the `--debug` flag to print extra debug information to the console.

Run with the `--reset` flag to clear the internal database and start fresh.

Example:
```
./magnet-onpremise/run --reset
```