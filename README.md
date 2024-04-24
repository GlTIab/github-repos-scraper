## GitHub Repositories Scraper From Any Profile

This Python script allows you to fetch all repositories of a GitHub user and save them to a text file.

### Prerequisites

- Python 3.x installed on your system.
- GitHub account.
- Personal access token generated from GitHub (https://github.com/settings/tokens/new)

### Installation

1. Clone or download the repository containing the script.
2. Ensure you have Python 3.x installed on your system.

### Usage

1. Open a terminal or command prompt.
2. Navigate to the directory containing the script.
3. Run the script using the following command:

```
python3 github-repos-scraper.py -username <GitHub_username> -token <GitHub_personal_access_token>
```
Replace ```<GitHub_username>``` with the username of the GitHub account whose repositories you want to fetch, and ```<GitHub_personal_access_token>``` with your actual personal access token generated from GitHub.

## Example

```python3 github-repos-scraper.py -username GlTIab -token YOUR_ACCESS_TOKEN```

Replace ```YOUR_ACCESS_TOKEN``` with your actual personal access token generated from GitHub.

## Output

The script will fetch all repositories associated with the provided GitHub username and save them to a text file named ```<GitHub_username>-repos.txt``` in the same directory as the script.

If successful, you will see a message indicating that the repositories have been saved to the file.

If no repositories are found for the provided username, a message indicating so will be displayed.

## Note
Ensure your personal access token has the necessary permissions to access the user's repositories.

Treat your personal access token as sensitive information and do not share it publicly.

For any issues or inquiries, feel free to contact us.

Enjoy exploring GitHub repositories with ease!
