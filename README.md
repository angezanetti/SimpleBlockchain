# Simple blockchain


This is a simple implementation of blockchain based on [Building a Blockchain](https://medium.com/p/117428612f46). 

The `blochain.py` contain the class of the blockchain mechanism, `api.py` is a minimal webserver to mine and retrieve blocks.
It's based on `Flask` and `python3.6`

## Installation

1. Make sure [Python 3.6+](https://www.python.org/downloads/) is installed. 
2. Install [pipenv](https://github.com/kennethreitz/pipenv). 

```
$ pip install pipenv 
```

3. Create a _virtual environment_ and specify the Python version to use. 

```
$ pipenv --python=python3.6
```

4. Install requirements.  

```
$ pipenv install 
``` 

5. Run the server:
    * `$ pipenv run python api.py` 
    
# Usage

### Mining
mining a block by making a `GET` request to `http://localhost:5000/mine`

### New transaction

You can create a new transaction by making a `POST` request on `http://localhost:5000/transactions/new`
The body should be:
```
'{
 "sender": "d4ee26eee15148ee92c6cd394edd974e",
 "recipient": "someone-other-address",
 "amount": 5
}'
```

You can also inspect the chain with `http://localhost:5000/chain`

### Nodes

You can register a new node on `http://localhost:5000/nodes/register`

And manage the conflicts on `http://localhost:5000/nodes/resolve`
