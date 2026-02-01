# LLM-driven Literature Review

An automated literature review tool based on Large Language Models (LLM) for extracting structured information from academic papers.

## Features

- Automatically read paper files and metadata
- Extract key information from papers using LLM API (research regions, data sources, core events, research methods, frequency ranges, research conclusions, etc.)
- Save extraction results in JSON format

## Requirements

- Python 3.11
- Required Python packages:
  - `openai` - For calling LLM API

## Installation

```bash
pip install openai
```

## Configuration

### ⚠️ Important: Configure API Key and Base URL

Before using this tool, you need to configure your API key and base_url in the main program.

Open `LLM-driven-litreview.ipynb`, find **Cell 8 (Main program)**, and fill in your configuration at the following location:

```python
# Main program
if __name__ == "__main__":
    # Configuration
    root_dir = 'mdstest'
    meta_path = "article_meta.bib"
    
    # ⬇️ Configure your API key and base_url here ⬇️
    api_key = "sk-your-api-key"  # Replace with your actual API key
    base_url = "https://api.moonshot.cn/v1"  # Replace with your API service URL
    # ⬆️ Configuration complete ⬆️
```

### Configuration Items

- **`api_key`**: Your LLM API key (e.g., Moonshot AI, OpenAI, etc.)
- **`base_url`**: Base URL of the API service
  - Moonshot AI: `https://api.moonshot.cn/v1`
  - OpenAI: `https://api.openai.com/v1`
  - For other providers, please refer to their documentation

### Other Configuration

- **`root_dir`**: Root directory where paper files are located (default: `'mdstest'`)
- **`meta_path`**: Path to paper metadata file (default: `"article_meta.bib"`)

## Usage

1. **Prepare files**:
   - Ensure paper files are stored in the `root_dir` directory according to the specified structure
   - Prepare paper metadata file (`.bib` format)

2. **Configure API**:
   - Fill in your `api_key` and `base_url` in the main program as described above

3. **Run the program**:
   - Execute all cells in the Jupyter Notebook in order
   - Or directly run the main program cell (Cell 8)

4. **View results**:
   - After the program finishes, it will generate `understandings.json` in the current directory
   - This file contains structured extraction results for all papers

## Output File

- **`understandings.json`**: Contains understanding results for all papers, formatted as a JSON array. Each element includes:
  - Research regions (location names and coordinates)
  - Data sources and time coverage
  - Core events (event type, time, location)
  - Research methods
  - Frequency ranges
  - Research conclusions (crustal velocity changes, main mechanisms, secondary mechanisms)
  - Discussion of conclusion uncertainties

## Notes

1. **API Key Security**:
   - Please keep your API key secure and do not commit it to public code repositories
   - It is recommended to use environment variables or configuration files to manage sensitive information

2. **API Call Limits**:
   - Be aware of API service rate limits and costs
   - The program includes a retry mechanism, but please control the batch processing quantity reasonably

3. **File Paths**:
   - Ensure all file paths are correct, especially `root_dir` and `meta_path`

## Project Structure

```
.
├── LLM-driven-litreview.ipynb  # Main program file
├── article_meta.bib            # Paper metadata file
├── example_understand.json    # Output format example
├── mdstest/                   # Paper files directory
└── README.md                   # This file
```

## License

Please add license information according to your actual situation.

## Contact

For questions or suggestions, please contact via Issues or Pull Requests.
