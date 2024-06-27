# chumba-trading

This repository contains code for a cryptocurrency trading bot that can be run on the live exchange e.g Bitget or binance

## Table of Contents

- [Installation](#installation)
- [Requirements](#requirements)
- [Additional code for aws](#additional code for aws)
- [License](#license)
- [Disclaimer](#Disclaimer)

## Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/chumbacash/chumba-trading.git
    cd chumba-trading
    ```

2. Create a virtual environment and activate it:

    ```bash
    python3 -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. Install the required packages:

    ```bash
    pip install -r requirements.txt
    ```

## Requirements
Python >= 3.12

## Additional code to be run on aws

1. what you need to know these promts for linux/ubuntu:

    You can replace the .pem file with yours then open the directory/command promt from where you saved the file usually to be placed on  (.ssh) folder.

    ```bash
    ssh -i "chumbacash-trading.pem" ubuntu@ec2-35-180-252-174.eu-west-3.compute.amazonaws.com
    ```
    Crontab -e will promt when youre running on your machine you can select 1 (I don't remember exactly what it was but 1 is great)

    ```bash
    crontab  -e 
    ```
    In this shell file you need to edit and save the files you want to run e.g run.py , run_btc.py and many more you can place the files to run here and it will follow the crontab inputs to ensure that it runs the task programmed. 

    ```bash
    bash chumba-trading/code/run_envelope.sh
    ```
    nano is used to navigate into the (.py) scripts. while (ls) is used to check the files in a paticular folder within where you're
    cd is to navigate
    cp run.py run_btc.py is like cloning the run.py script and creating a run_btc.py using the script you just created

    ```bash
    nano
    ls
    cd 
    cp run.py run_btc.py
    ```
    This is used to run your scripts after a paticular time e.g in the below script it will be used to run the script on the start of each candle or beginning of the hour

    ```bash
    0 * * * * bash LiveTradingBots/code/run_envelope.sh >> LiveTradingBots/envelope.log 2>&1
    ```
## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## By Amon (chumbacash) ✌🌷

This is not financial advice whatsoever; I created it for fun.

## Disclaimer
All this material is for educational and entertainment purposes only. It is not financial advice nor an endorsement of any provider, product or service. The user bears sole responsibility for any actions taken based on this information, and Chumbacash and its affiliates will not be held liable for any losses or damages resulting from its use. 
