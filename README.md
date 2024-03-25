# MultiPlayer-Quiz-Game

This is a simple quiz game implemented using socket programming in Python, consisting of a server (`server.py`) and a client (`client.py`). The game allows multiple clients to connect to the server, participate in a quiz, and answer questions to earn points. The server controls the flow of the quiz, manages participants, asks questions, and keeps track of scores.

## Files:

### `server.py`
- This file contains the implementation of the server side of the quiz game.
- It handles connections from multiple clients, manages participants, asks questions, and keeps track of scores.
- The server communicates with clients using sockets and `select` for handling multiple connections simultaneously.
- It randomly shuffles questions and answers from the `Questions.py` file for each round of the quiz.
- The server listens for connections on a specified IP address and port.

### `client.py`
- This file contains the implementation of the client side of the quiz game.
- It allows users to connect to the server by providing the server's IP address and port number as command-line arguments.
- Clients interact with the server by sending their name, receiving questions, buzzing to answer, and receiving feedback on their answers.

### `Questions.py`
- This file contains a list of questions, options, and correct answers for the quiz.
- Questions are stored as a list of lists, with each inner list containing the question, options, and correct answer.

## How to Run:

1. Ensure you have Python installed on your system.
2. Run `server.py` on a machine accessible to all players.
    ```
    python server.py <IP_address> <port_number>
    ```
    - Replace `<IP_address>` with the IP address of the machine running the server.
    - Replace `<port_number>` with the desired port number.
3. Run `client.py` on each player's machine.
    ```
    python client.py <server_IP_address> <server_port_number>
    ```
    - Replace `<server_IP_address>` with the IP address of the machine running the server.
    - Replace `<server_port_number>` with the port number specified for the server.
4. Follow the prompts to enter your name and participate in the quiz.

## Game Flow:

1. Participants join the quiz by connecting to the server.
2. Once the required number of participants has joined, the server starts the quiz.
3. Participants are presented with questions from the shuffled list.
4. Participants can buzz in to answer questions by hitting Enter.
5. If a participant answers correctly within the allotted time, they earn points.
6. The first participant to reach 5 points or more wins the game.
7. The server displays the scoreboard and announces the winner at the end of the quiz.

## Dependencies:

- The game requires Python 3.x to run.
- No additional external libraries are required.
