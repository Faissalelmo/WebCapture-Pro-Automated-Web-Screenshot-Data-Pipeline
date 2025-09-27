# social-monitoring-starter
# 🌐 WebCapture Pro: Automated Web Screenshot & Data Pipeline

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![PyQt5](https://img.shields.io/badge/PyQt5-5.15+-green.svg)

A powerful, modern desktop application that automates the process of capturing and processing web page screenshots at scale, with intelligent content detection and seamless API integration.

![Main Interface](social-monitoring-starter/main-interface.png)

## � Context & Problem Statement

In today's digital landscape, organizations face the challenge of systematically capturing and archiving web content from numerous sources. Manual screenshot capture is:
- Time-consuming and error-prone
- Difficult to scale for large numbers of URLs
- Inconsistent in quality and formatting
- Hard to integrate with existing data pipelines

WebCapture Pro solves these challenges by providing:
- Automated bulk screenshot capture
- Intelligent content detection
- Parallel processing capabilities
- Seamless API integration
- User-friendly interface

## ⚙️ Key Features

- 🎯 **Smart Content Detection**
  - Automatically identifies main content areas
  - Optimized for news sites and articles
  - Supports multiple content types

- 🚄 **High-Performance Processing**
  - Parallel processing with configurable workers
  - Batch processing capabilities
  - Rate limiting and error handling

- 🎨 **Modern User Interface**
  - Intuitive PyQt5-based GUI
  - Real-time progress tracking
  - Dark mode support
  - Drag-and-drop functionality

- 🔄 **API Integration**
  - Built-in REST API support
  - Customizable data mapping
  - Automatic error handling
  - Retry mechanisms

- 📊 **Advanced Features**
  - Multiple screenshot types (fullpage/content)
  - Various image formats (PNG/JPEG/WebP)
  - CSV data import/export
  - Detailed logging and reporting

## �️ Technology Stack

- **Frontend:**
  - PyQt5 for desktop interface
  - QWebEngine for web rendering
  - HTML5/CSS3 for modern UI components

- **Backend:**
  - Python 3.8+
  - Selenium WebDriver
  - Multi-threading
  - REST API integration

- **Data Processing:**
  - Pandas for data handling
  - PIL for image processing
  - Custom content detection algorithms

## �🚀 Getting Started

### Prerequisites
```bash
Python 3.8 or higher
pip (Python package manager)
Git
```

### Installation

1. Clone the repository
```bash
git clone https://github.com/yourusername/webcapture-pro.git
cd webcapture-pro
```

2. Install dependencies
```bash
pip install -r requirements.txt
```

3. Launch the application
```bash
python src/main_integrated.py
```
## 🏗️ Project Structure
```
Screenshot Automation Tool/
├─ README.md
├─ requirements.txt
├─ src/
│  ├─ __init__.py
│  └─ tools/
│     ├─ csv_screenshots.py
│     ├─ screenshots.py
│     └─ ui.py
```
## 🎯 Usage

Graphical Interface
```bash
python -m src.tools.ui
```
Command Line Screenshot Tool
```bash
python -m src.tools.csv_screenshots articles.csv \
  --url-column lien_web \
  --filename-column id \
  --support-column support_titre \
  --batch-size 5 \
  --max-workers 3 \
  --delay 0.5 \
  --screenshot-type content \
  --image-format jpg \
  --output-dir data/csv_screenshots_content
```
## 🛠️ Configuration

### CSV Format Requirements
Your CSV file should include these columns:

- `lien_web`: URL to capture

- `id`: Unique identifier for filename

- `support_titre`: Category for organizing screenshots

### Supported Moroccan News Websites

The tool includes optimized selectors for these Moroccan news portals:

- **Regional News**: `icirabat.com`, `icinador.com`, `icimeknes.com`
- **City Portals**: `icimarrakech.com`, `iciguercif.com`, `icifes.com`  
- **Local News**: `icidakhla.com`, `icicasa.com`, `iciagadir.com`
- **Media Networks**: `ichrakanews.com`, `i3lamtv.com`, `i3lam24.com`

And many more Moroccan/Arabic news sites with specialized content detection patterns.

## ⚙️ Advanced Options
### Screenshot Types
`fullpage`: Full webpage screenshot

`content`: Article content only (smart detection)

`both`: Both fullpage and content screenshots

### Image Formats
`png`: Lossless format, best for text

`jpeg`: Compressed format, smaller file size

`webp`: Modern format, good compression

### Performance Tuning
`--max-workers`: Number of parallel browsers (3-5 recommended)

`--delay`: Delay between requests to avoid rate limiting

`--batch-size`: Process in smaller batches for stability

## 🎯 Smart Content Detection
The tool uses multiple strategies to find article content:

1. Domain-specific selectors: Pre-configured for known sites

2. Generic patterns: Common article/content selectors

3. Aggressive detection: Text density and paragraph counting

4. Fallback methods: Full-page capture when content detection fails

## 📊 Output
### Screenshot Output
```batch
data/
├─ csv_screenshots/                # Default output directory
│  ├─ website_name/                # Organized by support_titre
│  │  ├─ fullpage/                 # Full page screenshots
│  │  └─ content/                  # Content-only screenshots
│  └─ screenshot_results_TIMESTAMP.csv  # Processing metadata
```
#### The results CSV includes:

- Original URL and metadata

- Screenshot file paths

- Success/failure status

- Processing time

- Error messages (if any)

## 🔧 Troubleshooting
### Common Screenshot Issues
1. Timeout errors: Increase delay or reduce max-workers

2. Empty screenshots: Check if website requires JavaScript

3. Popup interference: The tool automatically handles common popups

### Performance Tips
- Use --delay 1.0 for more reliable results

- Start with small --batch-size for testing

- Monitor memory usage with high --max-workers

## 🤝 Contributing

1. Improve selectors: Update existing configurations

2. Add features: Extend the base scraper or UI

3. Test thoroughly: Ensure compatibility with existing functionality

#### Contribution Process
1. Fork the repository

2. Create a feature branch

3. Add tests for new functionality

4. Submit a pull request

## 🆘 Support
For issues and questions:

Check the troubleshooting section above

Review the example commands

Ensure all dependencies are installed

### Happy scraping! 🚀
