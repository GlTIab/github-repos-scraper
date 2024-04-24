import argparse
import requests
import os

def get_github_repos(username, token):
    url = f"https://api.github.com/users/{username}/repos"
    repos = []

    # Fetch all repositories using pagination
    while url:
        headers = {"Authorization": f"token {token}"}
        response = requests.get(url, headers=headers)
        if response.status_code == 200:
            data = response.json()
            repos.extend([repo["html_url"] for repo in data])
            # Check if there are more pages
            url = response.links.get('next', {}).get('url')
        else:
            print(f"Failed to fetch repositories for {username}. Status code: {response.status_code}")
            break

    return repos

def save_to_file(repos, filename):
    with open(filename, 'w') as file:
        for repo in repos:
            file.write(repo + '\n')

if __name__ == "__main__":
    parser = argparse.ArgumentParser(description="GitHub Repos Parser")
    parser.add_argument("-username", help="GitHub username")
    parser.add_argument("-token", help="GitHub personal access token")
    args = parser.parse_args()

    if args.username and args.token:
        repos = get_github_repos(args.username, args.token)
        if repos:
            target_file = f"{args.username}-repos.txt"
            save_to_file(repos, target_file)
            print(f"Repositories saved to {target_file}")
        else:
            print("No repositories found.")
    else:
        print("Please provide the GitHub username and personal access token.")
