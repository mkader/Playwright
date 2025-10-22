https://www.youtube.com/@Playwrightdev


## VSC Setup for Playwright MCP

1. Create a prompt file (\playwright_mcp\.github\prompts\generate.prompt.md)
```
    - You are given a scenario and you need to generate a playwright test for it.
    - DO NOT generate test code based on the scenario alone. 
    - DO run steps one by one using the tools provided by the Playwright MCP.
	- Only after all steps are completed, emit a Playwright TypeScript test that uses @playwright/test based on message history
	- Save generated test file in the tests directory
	- Execute the test file and iterate until the test passes
```

2. Create an MCP configuration file (\playwright_mcp\.vscode\mcp.json)
```
    {
        "servers": {
            "playwright": {
                "command": "npx",
                "args": [
                    "@playwright/mcp@latest"
                ]
            }
        }
    }
```

3. Open a new Chat Editor in VS Code
    1. Add the context file: generate.prompt.md
    2. In the chat input, enter the following prompt:
```
        Generate a Playwright test for the following scenario:
        1. Navigate to https://demo.playwright.dev/movies
        2. Search for 'Garfield'
        3. Verify that the movie appears in the list
```
4. Follow the instructions
   
![alt text](1.vsc_setup_playwright_mcp.png)
--------------------------
