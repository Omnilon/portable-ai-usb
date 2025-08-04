# Portable AI USB

Advanced yet user‑friendly portable AI application that runs from a USB drive and starts automatically once connected to the internet.

## Features

* **Internet detection** – waits for an internet connection before launching the AI service.
* **Web interface** – provides a lightweight web UI via Flask, accessible at `http://localhost:5000`.
* **OpenAI integration** – uses OpenAI’s GPT models to answer your questions.
* **Portable** – designed to live on a USB drive alongside a portable Python distribution.
* **Easy launch scripts** – includes Windows (`launch.bat`) and Unix (`launch.sh`) launchers.

## Installation

1. **Prepare Python.** Install a portable Python distribution on your USB drive (for example, [WinPython](https://winpython.github.io/) for Windows) or ensure Python 3.8+ is available on the host machine.
2. **Install dependencies.** In your portable Python environment, install the packages listed in `requirements.txt`:

   ```sh
   pip install -r requirements.txt
   ```

3. **Set your OpenAI API key.** Export your API key as an environment variable before running the assistant:

   * **Windows (Command Prompt):**
     ```cmd
     set OPENAI_API_KEY=sk‑...
     ```
   * **PowerShell:**
     ```powershell
     $env:OPENAI_API_KEY="sk‑..."
     ```
   * **Unix/Linux/macOS:**
     ```sh
     export OPENAI_API_KEY=sk‑...
     ```

   Without an API key the assistant will return an error message instead of AI‑generated responses.

## Usage

1. Plug the USB drive into a computer with internet access.
2. On Windows, double‑click `launch.bat`. On macOS/Linux, run:

   ```sh
   ./launch.sh
   ```

3. The script will wait until an internet connection is detected, then start a local web server.
4. Open your browser to `http://localhost:5000` and enter your question or prompt.

### Autorun considerations

Due to security restrictions, modern operating systems disable automatic execution of programs from USB drives. You’ll typically need to run the launcher manually. Be cautious of any changes to system settings that re‑enable autorun, as they can pose security risks.

## Customization

* **Model selection:** To change the AI model (for example, to use `gpt‑4`), modify the `model` parameter in `run_ai.py`.
* **Offline functionality:** To add offline capabilities, you could integrate a local model via the `transformers` library. This requires additional setup and storage space.
* **User interface:** Feel free to extend the Flask application or replace it with a different framework to create a more sophisticated UI.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
