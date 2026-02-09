# CalQlator
<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=c-sharp&logoColor=white" alt="C#">
  <img src="https://img.shields.io/badge/.NET-512BD4?style=for-the-badge&logo=dotnet&logoColor=white" alt=".NET">
  <img src="https://img.shields.io/badge/Qt-41CD52?style=for-the-badge&logo=qt&logoColor=white" alt="PyQt5">
  <img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black" alt="Linux">
  <img src="https://img.shields.io/badge/macOS-000000?style=for-the-badge&logo=apple&logoColor=white" alt="macOS">
</p>

CalQlator is a powerful, cross-platform calculator application capable of performing operations in multiple numeric systems: **Binary (BIN)**, **Octal (OCT)**, **Decimal (DEC)**, and **Hexadecimal (HEX)**. 

Beyond standard arithmetic, it features **Voice Control**, allowing users to perform calculations hands-free.

<p align="center">
  <img src="docs/test.gif" alt="CalQlator Demo">
</p>

## ✨ Features

*   **Multi-Base Arithmetic**: Seamlessly switch between and calculate in BIN, OCT, DEC, and HEX systems.
*   **Voice Commands**: Integrated speech recognition allows you to speak your equations (e.g., "Five plus three equals").
*   **Advanced Operations**: Includes Factorial, Exponentiation, Roots, Inverse, and more.
*   **Cross-Platform**: Optimized for both macOS and Linux environments.
*   **Responsive UI**: Clean interface built with PyQt5.

## 🚀 Technical Highlights

This project demonstrates a robust implementation of modern software engineering principles:

*   **Hybrid Architecture**: Combines the rapid UI development of **Python (PyQt5)** with the type safety and performance of **C# (.NET Core)** for the backend logic.
*   **Interoperability**: Utilizes `pythonnet` (CLR) to bridge Python's flexibility with C#'s structural strengths.
*   **Clean Architecture & Design Patterns**:
    *   **MVC (Model-View-Controller)**: Strict separation of concerns ensures code maintainability and testability.
    *   **Factory Pattern**: Dynamically creates operation instances in C# for cleaner extensibility.
    *   **Strategy Pattern**: Handles logic for different numeric systems efficiently.
*   **Extensible Configuration**: Voice commands are mapped via a JSON dictionary (`Controllers/dictionary.json`), allowing for easy customization and localization.
*   **Threaded Performance**: Voice processing runs on separate threads, ensuring the UI remains responsive during heavy tasks.

## 🛠 Built With

*   **[Python 3](https://www.python.org/)**: Application Logic and Voice Controller.
*   **[C# (.NET Core)](https://docs.microsoft.com/en-us/dotnet/csharp/)**: Core Mathematical Models and Business Logic.
*   **[PyQt5](https://riverbankcomputing.com/software/pyqt/intro)**: Graphical User Interface.
*   **[SpeechRecognition](https://pypi.org/project/SpeechRecognition/)**: Voice processing library.
*   **[Python.NET (pythonnet)](http://pythonnet.github.io/)**: Integration layer between Python and .NET.

## 📦 Getting Started

### Installing

**Linux**
Run the pre-built binary:

```sh
curl -L "https://raw.githubusercontent.com/juanchavezcornejo/CalQlator/master/dist/CalQlator" -o CalQlator
chmod +x CalQlator
./CalQlator
```

**macOS**
Checkout the app bundle:

```sh
svn checkout "https://github.com/juanchavezcornejo/CalQlator/trunk/dist/CalQlator.app"
open CalQlator.app
```

### Development & Execution

Prerequisites:
*   Python 3.x
*   .NET SDK

```sh
# 1. Install Python dependencies
pip3 install -r requirements.txt

# 2. Build the C# Model
dotnet build Models/Models.csproj --configuration Release --output build/

# 3. Run the Application
python3 main.py
```

### Build it yourself (Standalone Executable)

To create a standalone executable using [PyInstaller](https://www.pyinstaller.org/):

```sh
pip3 install -r requirements.txt
dotnet build --configuration Release --output build/
python3 main.py
pyinstaller CalQlator.spec
```

## 🏗 Architecture

### Models (C#)
The core logic of the application resides in C#. This ensures type safety and high performance for complex calculations.

![](docs/ModelsClassDiagram.jpg)

### Controllers (Python)
The pure Python layer that acts as the bridge between the UI and the Data.

*   **Main Controller**: Manages application state and user input.
*   **Voice Controller**: Handles audio recording, speech-to-text validation, and command execution.
    *   **Usage**: Speech keywords are configurable in `Controllers/dictionary.json`.

### Views (Python + PyQt)
The presentation layer is built with PyQt5, providing a native look and feel across platforms.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
