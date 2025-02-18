# C Programming template guide

## 1. Installing Required Software

### Ubuntu/Debian:
```bash
# Update package list
sudo apt update

# Install GCC compiler and build tools
sudo apt install build-essential

# Install CMake
sudo apt install cmake
```

### macOS:
```bash
# Install Homebrew if not already installed
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Install GCC
brew install gcc

# Install CMake
brew install cmake
```

## 2. VS Code Setup

1. Install VS Code from https://code.visualstudio.com/

2. Install required extensions:
   - C/C++ Extension Pack (Microsoft)
   - CMake Tools (Microsoft)

To install extensions:
1. Open VS Code
2. Press `Ctrl+Shift+X` (Windows/Linux) or `Cmd+Shift+X` (macOS)
3. Search for each extension and click "Install"

## 3. Building and Running the Project

### Using VS Code:

1. Open the project folder in VS Code:
   ```bash
   code /path/to/template_folder
   ```

2. When prompted "Would you like to configure this project?", click "Yes"

3. Select "GCC" as the compiler when prompted

4. Click the "Build" button in the bottom status bar or press `F7`

5. To run the program:
   - Open a terminal in VS Code (`Ctrl+` `)
   - Run: `./build/your_program_name`

### If you prefer using the terminal:

```bash
# Create and enter build directory
mkdir build && cd build

# Generate build files
cmake ..

# Build the project
make

# Run the program
./your_program_name
```

## 4. Submitting Your Project

The built executable will be located in the `build` directory. You can submit this executable along with any additional files required for your project.
