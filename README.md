
# Find Duplicate Video Files

This repository contains a Bash script (`find_duplicates.sh`) that finds and lists duplicate video files in a specified directory. It also calculates a quality score for each video and determines the best version to keep based on video resolution, bitrate, duration, and codec type.

## Table of Contents
1. [Features](#features)
2. [Requirements](#requirements)
3. [Installation](#installation)
4. [Configuration](#configuration)
5. [Usage](#usage)
6. [Logging](#logging)
7. [File Output](#file-output)
8. [License](#license)

---

## Features
- Scans a directory for video files (`.mkv`, `.mp4`, `.avi`, `.ts`)
- Identifies potential duplicate files based on filename
- Calculates a quality score for each video to determine the best version to keep
- Logs actions and errors to a log file
- Outputs a summary of duplicate video files

## Requirements
- Bash (Linux/macOS)
- `ffprobe` (part of FFmpeg, used to extract video properties)

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/find-duplicates.git
   cd find-duplicates
   ```
2. Make the script executable:
   ```bash
   chmod +x find_duplicates.sh
   ```

3. Install FFmpeg if it's not already installed:
   ```bash
   sudo apt-get install ffmpeg
   ```
   Or for macOS:
   ```bash
   brew install ffmpeg
   ```

## Configuration
- **Log File Path**: The script saves logs to `$HOME/logs/duplicates_log.txt`. You can modify this path as needed.
- **Search Directory**: By default, the script searches the `/mnt/Media` directory for video files. Update the `search_dir` variable to change this directory.
- **Output Directory**: Results are saved in your home directory by default (`$HOME`). Update the `output_dir` variable to change the output location.

## Usage
Run the script with the following command:
```bash
./find_duplicates.sh
```

### Script Actions
- The script will search for video files in the specified `search_dir`.
- It will identify duplicate filenames, calculate a quality score for each video, and write the results to a text file (`Duplicates.txt`) in the `output_dir`.

## Logging
- The script logs its actions and any errors to a log file located at `$HOME/logs/duplicates_log.txt`.
- The log file records:
  - Files found in the search directory
  - Potential duplicate filenames
  - The results of the duplicate detection process

## File Output
- **Duplicates.txt**: This file is saved in the `output_dir` and contains a summary of the duplicate video files found. The summary includes:
  - **Count**: Number of duplicates found for a filename
  - **Name**: Filename of the duplicate video
  - **Group**: Paths to all duplicates
  - **Best Quality**: The file with the highest quality score
  - **Best Quality Score**: The calculated score of the best-quality file

## License
This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

