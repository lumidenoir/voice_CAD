# Voice-Enabled CAD System

## Overview

This project is a voice-enabled CAD (Computer-Aided Design) system that uses a Rust backend server to process requests and a speech recognition system in Python to convert voice commands into text. The speech recognizer is trained on customized data to ensure accurate transcription of CAD-specific commands.

## Features

- **Voice Command Interface**: Allows users to interact with the CAD system using natural language commands.
- **Rust Backend**: A fast and efficient server that handles CAD operations and processes voice command requests.
- **Speech-to-Text (STT)**: A Python-based speech recognition system trained on a custom dataset to accurately recognize CAD-specific commands and generate STT files.
- **Real-Time Processing**: Immediate response to voice commands with minimal latency.

## Architecture

1. **Voice Command Input**: The user speaks a command.
2. **Speech Recognition**: The Python speech recognizer processes the command and generates an STT file.
3. **Rust Backend**: The STT file is sent to the Rust server, which interprets the command and performs the corresponding CAD operation.
4. **CAD Operation**: The result is displayed to the user or further processed as needed.

## Prerequisites

- **Rust**: Installed on your system. [Installation Guide](https://www.rust-lang.org/tools/install)
- **Python 3.x**: Installed with necessary packages. (Refer to the `requirements.txt` file)
- **Customized Speech Recognition Data**: Prepare a dataset specific to CAD commands and train the speech recognizer.

## Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/voice-enabled-cad.git
   cd voice-enabled-cad
   ```

2. **Set Up the Python Environment**
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
   ```

3. **Train the Speech Recognizer**
   - Place your customized data in the `data/` directory.
   - Run the training script:
     ```bash
     python train_speech_recognizer.py
     ```
   - The trained model will be saved in the `models/` directory.

4. **Build and Run the Rust Server**
   ```bash
   cd rust-backend
   cargo build --release
   ./target/release/voice_cad_server
   ```

## Usage

1. **Start the Rust Backend**
   - Make sure the Rust server is running as described in the installation section.

2. **Run the Speech Recognizer**
   ```bash
   python recognize_and_send.py
   ```

3. **Speak Commands**
   - Use voice commands like "draw a line", "rotate object", etc.
   - The command will be processed, and the CAD operation will be executed.

## Configuration

- **Backend Configuration**: Modify `config.toml` in the `rust-backend` directory for server settings.
- **Speech Recognizer Configuration**: Adjust parameters in `config.json` within the Python directory to fine-tune the recognition process.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request on GitHub.

## License

This project is licensed under the MIT License.


