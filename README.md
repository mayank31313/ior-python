Repository for the python client

### Prerequisite

<ul>
<li>Docker</li>
<li>Python 3</li>
</ul>

## Server Setup (Quick Start)

    cd ~
    mkdir controlnet-docker
    cd controlnet-docker
    wget https://mayank31313.github.io/docker/socket_server/docker-compose.yml
    
    docker-compose up

## Client (Quick Start)

For this example no external configuration is needed, all the settings are predefined. The below example will only give a use case on the controlnet platform.

    git clone https://github.com/mayank31313/ior-python
    cd ior-python/examples
    python3 LatencyCheck.py
    
## Installation
Run the following command

    python3 setup.py install
 
## Usage

    config = {
        "server": "localhost",
        "httpPort": 5001,
        "socketServer": "localhost",
        "tcpPort": 8000,
        #"useSSL": True    # Optional
    }
    
## Create Instance of IOT Client

    from ior_research.IOTClient import IOTClientWrapper
    iot = IOTClientWrpper(token=token, config = config) #Creating object for IOT Client

### Setting up Receive Function to do some Operation when a response is received.

    iot.set_on_receive(lambda x: print(x))

### Last but not the least start the IOTClient

    iot.start()
    iot.join() #Since IOTClient inherites Thread Class you can also use .join() function depending on your use case


    


