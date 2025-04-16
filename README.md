# RandomHomers

A fantasy baseball web scraper that identifies hot hitters and randomly recommends players to consider for your fantasy lineup. This tool scans baseball statistics websites to find the most frequently mentioned hitters who are performing well, then randomly selects a subset to help with your daily fantasy decisions.

## Features

- 🔍 Scrapes fantasy baseball websites for player performance data
- 📊 Identifies players with the most home runs over different time periods
- 🎲 Randomly selects players to consider for your fantasy lineup
- 📝 Saves results to a text file with current date
- 🖼️ Takes screenshots for verification and debugging
- 🚀 User-friendly command-line interface with colorful output

## Requirements

- Python 3.11+
- pip package manager
- Playwright for browser automation
- NLTK for text processing

## Installation

1. Clone this repository:
```bash
git clone https://github.com/elblanco2/RandomHomers.git
cd RandomHomers
```

2. Set up the environment:
```bash
# Make scripts executable
./fix_permissions.sh

# Run the installer script
./install.sh
```

3. Download required NLTK data:
```bash
./download_nltk.sh
```

## Usage

Run the scraper with default settings:
```bash
./run_scraper.sh
```

The script will:
1. Launch a browser and navigate to the fantasy baseball website
2. Extract text and identify player names
3. Randomly select 4 players from the top performers
4. Save the results to a text file in the `results` directory

### Command-line Options

```bash
./run_scraper.sh [OPTIONS]
```

Options:
- `--url URL`: Scrape a different URL (default: https://www.onlyhomers.com/fantasy)
- `--output-dir DIR`: Change output directory (default: ./results)
- `--count N`: Number of players to select (default: 4)
- `--dry-run`: Run without writing to file

## Troubleshooting

If you encounter issues:

1. Make sure all required NLTK data is downloaded:
```bash
./download_nltk.sh
```

2. Run the diagnostic script:
```bash
./diagnose.sh
```

3. Check the screenshot.png file to verify scraping results

4. Review the log file (fantasy_scraper.log) for detailed error messages

## Project Structure

- `fantasy_scraper.py`: Main script that handles web scraping and orchestration
- `player_extractor.py`: Specialized module for identifying baseball player names
- `download_nltk.py`: Script to download required NLTK data packages
- `run_scraper.sh`: User-friendly runner script
- `install.sh`: Installation script for dependencies
- `fix_permissions.sh`: Script to set correct file permissions
- `diagnose.sh`: Diagnostic tool for troubleshooting
- `test_local.sh`: Test script using local HTML instead of live website
- `results/`: Directory where output files are saved

## Version History

- v1.0 (Apr 2025): Initial release with player name extraction from OnlyHomers

## License

MIT

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Acknowledgements

- [OnlyHomers](https://www.onlyhomers.com/) for baseball statistics
- [Playwright](https://playwright.dev/) for web automation
- [NLTK](https://www.nltk.org/) for natural language processing
