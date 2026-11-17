# Gonic - The PyQt for Go

## Windows 11: clone, install and run (PowerShell)

This is a **Go** project. You do not need Python, pip, venv, or npm. Install Git and Go (the repository currently declares Go 1.18 as its minimum in the root module; a current Go toolchain is recommended). Run the following commands **one at a time**:

```powershell
go version
```

```powershell
git clone https://github.com/Tyler-Keesee/GONIC-GO-GUI-.git
```

```powershell
Set-Location .\GONIC-GO-GUI-
```

```powershell
go mod download
```

```powershell
Set-Location .\cmd
```

```powershell
go mod download
```

```powershell
go run .
```

The `cmd` directory has its own `go.mod`. Start the example from `cmd`, not from the repository root. GUI rendering depends on system graphical libraries and drivers; on Windows it needs a desktop session.

**Verification:** `go version` and `go mod download` only verify tools/dependencies. A successful `go run` is the local smoke test. If you see compile errors, include the exact Go version, current folder, and first compiler error. Do not run `go mod tidy` blindly just to make the clone start, since it rewrites module files.

---


<p align="center">
  <strong>Beautiful, Simple, Pure Go GUI Framework</strong>
</p>

<p align="center">
  <a href="#installation">Installation</a> •
  <a href="#project-structure">Project Structure</a> •
  <a href="#running-examples">Running Examples</a> •
  <a href="#usage">Usage</a> •
  <a href="#components">Components</a> •
  <a href="#roadmap">Roadmap</a>
</p>

Gonic is a modern, lightweight GUI framework designed specifically for Go developers who want simplicity without sacrificing power. It's the PyQt5 of Go: easy to install, powerful to use, and beautiful out of the box.

## Installation

### Clone the Repository

```bash
# Clone the repository
git clone https://github.com/Tyler-Keesee/GONIC-GO-GUI-
cd GONIC-GO-GUI-

# Install dependencies 
go mod tidy
```

### Using as a Package (Coming Soon)

The `go.mod` currently declares the local module name `gonic`, not the GitHub import path. Until the module path and published API are reconciled and tested, **clone the repository** rather than using `go get` as an installation instruction.

## Project Structure

The project is organized as follows:

- `/api.go` - Main framework API
- `/components/` - UI components like buttons, labels, etc.
- `/layout/` - Layout managers for organizing components
- `/internal/` - Rendering backends (Fyne and web)
- `/themes/` - Theme definitions
- `/examples/` - Example applications
- `/cmd/` - Command-line tools and demo app
- `/standalone/` - Standalone demo using Fyne directly

## Running Examples

Make sure to run `go mod tidy` in each directory before running examples.

### Main Demo

```bash
cd cmd
go mod tidy
go run .
```

### Web Demo

```bash
cd cmd/htmlgui
go mod tidy
go run .
```

### Counter Example

```bash
cd examples/counter
go mod tidy
go run .
```

### Dashboard Example

```bash
cd examples/dashboard
go mod tidy
go run .
```

### Standalone Fyne Example

```bash
cd standalone
go mod tidy
go run .
```

## Usage

Getting started is incredibly simple:

```go
package main

import (
    "fmt"
    "gonic"
)

func main() {
    app := gonic.NewApp()
    win := gonic.NewWindow("My App", 800, 600)
    app.AddWindow(win)

    win.SetContent(
        gonic.NewStackLayout().Add(
            gonic.NewLabel("Hello, World!"),
            gonic.NewButton("Click Me", func() {
                gonic.Alert("You clicked the button!")
            }),
        ),
    )

    app.Run()
}
```

## Components

Gonic comes with a growing library of components:

- Windows and Dialogs
- Buttons and Labels
- Input fields and Forms
- Layouts (Stack, Flex, Grid)
- Menus and Navigation
- Tables and Lists
- And more coming soon!

## Renderers

Gonic supports multiple rendering backends:

1. **Web Renderer**: Renders the UI in a web browser using HTML/CSS
2. **Native Renderer**: Uses Fyne to provide native UI components

The framework automatically chooses the best renderer based on your environment, or you can specify which one to use.

## Roadmap

- [x] Core Window Management
- [x] Basic Components (Button, Label, Input)
- [x] Layout System
- [x] Theming System
- [ ] Data Binding
- [ ] State Management
- [ ] Built-in Charts
- [ ] WASM Support for Web Deployment
- [ ] Animation System
- [ ] Accessibility Features

## Contributing

Contributions are very welcome! Check out the issues page for ideas on where to start, or propose your own improvements.

### Pushing Changes to GitHub

If you've made changes to the codebase and want to push them:

```bash
# Initialize git if not already done
git init

# Add all files
git add .

# Commit your changes
git commit -m "Your commit message"

# Add the remote repository (if not already set)
git remote add origin https://github.com/Tyler-Keesee/GONIC-GO-GUI-.git

# Push to GitHub
git push -u origin main
```

## License

No `LICENSE` file is committed currently. Terms are not specified; add a full license file if MIT licensing is intended.

---

<p align="center">Built with ❤️ for the Go community</p> 
# GONIC-GO-GUI-
GONIC a GO GUI  
