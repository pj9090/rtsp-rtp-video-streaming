# RTSP and RTP streaming

 Python implementation of the programming assignment 6 of Foundations of Networks course at RIT
 
 Implements basic RTSP and RTP streaming functionality using the standard Python 3 library, plus [PyQt5](https://pypi.org/project/PyQt5/) and [Pillow](https://github.com/python-pillow/Pillow) for stuff related to GUI. Error handling is very minimal, reopening the server and client is required to run another session.


## Installation

Clone the repository.

Having python>=3.6 installed, create a virtual environment by running `python -m venv venv` inside the cloned folder.

Activate the virtual environment (`source venv/bin/activate` on Linux, `.\venv\Scripts\activate` on Windows).

Install the requirements with `python -m pip install -r requirements.txt`.

## Usage

Go to the sources folder with `cd src/` (video stream class assumes `mjpeg` file is in working directory).

Server should be run first with 
```
python main_server.py <port> 
```
In which `port` is the port number for the RTSP socket to listen on.

Client can then be run with 
```
python main_client.py <file name> <host address> <host port> <RTP port>
```
in which `file name` is the name for the file to be sent via RTP (`movie.mjpeg` is the available sample), `host address` is the server address (`localhost` if running on same machine), `host port` is the port selected when running the server, `RTP port` is the port for receiving the video via RTP.

Since you're probably running each instance on separate terminals, remember to activate the venv on both.

Suggested configs are:
```
python main_server.py 5540
python main_client.py movie.mjpeg localhost 5540 5541
```
