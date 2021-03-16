[![Flask Change Microservice Test](https://github.com/noahgift/flask-change-microservice/actions/workflows/main.yml/badge.svg)](https://github.com/noahgift/flask-change-microservice/actions/workflows/main.yml)

# flask-change-microservice
Small Flask Microservice that makes change

*Coursera Lab:  duke-coursera-ccb-lab2*

![coursera-lab](https://user-images.githubusercontent.com/58792/108137449-df0e0300-7089-11eb-8b11-74f478b71d11.png)


## Invoke Endpoint

* Create virtualenv and source it: `python3 -m venv ~/.fcm && source ~/.venv/bin/fcm`
* Install and Test:  `make all`
* Run it:  `python app.py`
* Invoke it.  Options include curl, Postman, httpie.  These methods are documented below


### Curl

`curl http://127.0.0.1:8080/change/1/34`

```bash
[
  {
    "5": "quarters"
  }, 
  {
    "1": "nickels"
  }, 
  {
    "4": "pennies"
  }
]
```
### httpie

[Installation of httpie](https://httpie.io/docs#installation)

`http 127.0.0.1:8080/change/1/34`

```bash
HTTP/1.0 200 OK
Content-Length: 90
Content-Type: application/json
Date: Tue, 16 Mar 2021 16:49:11 GMT
Server: Werkzeug/1.0.1 Python/3.9.0

[
    {
        "5": "quarters"
    },
    {
        "1": "nickels"
    },
    {
        "4": "pennies"
    }
]
```


### Postman

[Install Postman](https://www.postman.com)
![postman](https://user-images.githubusercontent.com/58792/111342614-00461d00-8651-11eb-8433-d7d91d3e48b4.png)

### Requests

The [Python requests library](https://requests.readthedocs.io/en/latest/user/quickstart/) allows you to invoke a request as a "one-liner" or a script.

`python -c "import requests;r=requests.get('http://127.0.0.1:8080/change/1/34');print(r.json())"`

Result:

`[{'5': 'quarters'}, {'1': 'nickels'}, {'4': 'pennies'}]`

## Loadtest with Locust

* [Install Locust](https://github.com/locustio/locust)
* Create a `locustfile.py`
* Run loadtests
![Screen Shot 2021-03-16 at 3 02 59 PM](https://user-images.githubusercontent.com/58792/111367175-d7328600-866a-11eb-9a4d-3429710593ea.png)
![Screen Shot 2021-03-16 at 3 02 35 PM](https://user-images.githubusercontent.com/58792/111367176-d7328600-866a-11eb-9856-928d42e65a9a.png)
![Screen Shot 2021-03-16 at 3 01 22 PM](https://user-images.githubusercontent.com/58792/111367178-d7cb1c80-866a-11eb-8c29-6440a6179544.png)




