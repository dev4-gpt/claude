# claude code

`curl -fsSL https://claude.ai/install.sh | bash`

## Disk Space

In terminal:

`ollama list`

see model CPU/GPU usage
`ollama ps && ollama show qwen3-coder:30b` (FAILS)

`df -h /`

`du -sh ~/.ollama/models`

general disk space
`du -h -d 1 ~ | sort -h`

npm cache
`npm cache clean --force`

## Launch claude without pro/max/enterprise key or api

`ollama launch claude --config`

Checking MEMORY
`top -l 1 -o cpu -n 5 && echo "--- MEMORY ---" && top -l 1 -o mem -n 5 && echo "--- SWAP ---" && vm_stat | grep "Pageout"`
`ps aux | grep ollama | grep -v grep`

`ollama pull qwen2.5-coder:7b` (DUMB model)

`ollama rm gemma3:4b` (DUMB model)


<img width="997" height="567" alt="Screenshot 2026-02-07 at 4 27 20 PM" src="https://github.com/user-attachments/assets/8bc68884-73f6-4011-9dd3-1179422c04e2" />



<img width="1162" height="405" alt="Screenshot 2026-02-07 at 4 28 25 PM" src="https://github.com/user-attachments/assets/7a58aa40-bb4e-4eb5-9997-e141955b5e35" />



<img width="1173" height="541" alt="Screenshot 2026-02-07 at 4 29 25 PM" src="https://github.com/user-attachments/assets/37cb0cbc-cbf0-4e42-a486-f755350e509f" />



<img width="901" height="488" alt="Screenshot 2026-02-07 at 4 29 54 PM" src="https://github.com/user-attachments/assets/3f25a2b1-dc17-4222-8b32-43c8e189e5cc" />



<img width="1127" height="507" alt="Screenshot 2026-02-07 at 4 30 48 PM" src="https://github.com/user-attachments/assets/4bc4bf86-1f7a-47eb-ac43-a493f8d395a3" />



(FOR ~16GB RAM)
Check the parameter size (B): Multiplying the "B" number by 0.7 gives you the approximate GB of RAM it needs.
7B x 0.7 = ~5 GB (Safe ✅)
14B x 0.7 = ~10 GB (Risky/Slow ⚠️ - leaves only 6GB for macOS)
30B x 0.7 = ~21 GB (Impossible ❌ - will freeze)


Diagrammatic representation of flow =

D3.js or recharts (web app)

  A[User Input] --> B[State Update: handleQueryChange];   
  
    B --> C[Redux Store Update];     
    
    C --> D[Dispatching Action: fetchData];   
    
    D --> E[Axios API Call];        
    
    E --|{FETCH_DATA_SUCCESS}| F[Express Server Middleware];
    
    E --|{FETCH_DATA_FAILURE}| G[Error Handling & Response];
    
    F --> H[Data Fetching: MongoDB Query];
    
    H --|{Success}| I[Data Processing & Sending];
    
    H --|{Failure}| J[Error Handling & Response];
    
    I --|{Success}| K[API Response Handling];
    
    K --> L[Data Update & Display];
    
    G --> K;
    
    J --> K;

https://app.eraser.io/workspace/icUk39WGeHzHH7gCtFKN?origin=share

<img width="2310" height="2142" alt="diagram-export-2-10-2026-11_12_07-PM" src="https://github.com/user-attachments/assets/6955acc8-d2ec-44f9-bb9e-edc498748bac" />


## Claude Code 

`/init` = memory; analyze codebase to understand what it should know every time running the code

Claude.md = lint, memory


<img width="775" height="333" alt="Screenshot 2026-02-11 at 1 55 23 PM" src="https://github.com/user-attachments/assets/9153bf91-9d56-4aea-9ce6-da661547a74d" />


find . -name "*.json" -o -name "Makefile" -o -name "tox.ini" -o -name "pytest.ini" -o -name ".env*" 2>/dev/null  

`/ide` = sets VScode connection with claude code in terminal; context of certain files and asking questions is possible

`#` for setting memory in claude code [only with max or pro. not free models]

Eg, "# always use uv to run the server and dont use pip directly"
./CLAUDE.local.md = Project memory (local), 
~/.claude/CLAUDE.md = user memory in, \project memory in ./CLAUDE.md . Add all three       
  options in readme with code  

`/help`
`/memory`
`/mcp`
`/agents`
`/clear` = clear context window and start fresh
`/compact` = clear the history but keep a summary


<img width="638" height="393" alt="Screenshot 2026-02-12 at 2 42 19 PM" src="https://github.com/user-attachments/assets/c72280e3-c516-447a-8df9-0b9e0faa36f2" />

<img width="646" height="220" alt="Screenshot 2026-02-12 at 2 43 38 PM" src="https://github.com/user-attachments/assets/1981afff-e957-4d8f-acd4-4a607ec0d0de" />

PLAN MODE = SHIFT+TAB*2
ACCEPT EDITS = SHIFT+TAB

Eg, The chat interface displays query responses with source citations. I need to modify it so each source        
  becomes a clickable link that opens the corresponding lesson video in a new tab: - When courses are          
  processed into chunks in @backend/document_processor.py, the link of each lesson is stored in the course     
   catalog collection; - modify _format_results in @backend/search_tools.py so that the lesson links are       
  also returned; - the links should be embedded invisibly (no visible URL text) 


## .vscode 

`settings.json`
{
    "python.analysis.typeCheckingMode": "basic"
}

## Push to Github from CLI

`git add .`

`git commit -m "..."`

`git push origin main`


## MCP Tool call to claude code

gain additional functionality to external sources and systems

eg, Playwright
`claude mcp add name_of_mcp underlying_command_to_start_mcp`
`claude mcp remove name_of_mcp`

name_of_mcp = playwright
underlying_command_to_start_mcp = npx @playwright/mcp@latest

## Claude Code prompt for frontend= 

"using the playwright mcp server visit *site_we_are_at* and view the new chat button. I want that button to look the same as the other links below for Courses and Try asking. Make sure that it is left aligned and that the border is removed."

site_we_are_at = http://127.0.0.1:8000/


NOTE: Models like mistral-nemo:latest and qwen2.5-coder:7b failed to work with tools like /mcp and follow simple guidelines like making a flowchart, or accessing multiple folders like @frontend and @backend. Would suggest get an ANTHROPIC_API_KEY.

## Claude Code prompt for frontend

"In @backend/search_tools.py, add a second tool alongside the existing content related tool. This new tool should handle course outline queries - 
1. functionality:
   a. input:course title,
   b. output:course title, course link, and complete lesson list,
   c. For each lesson, add lesson number and lesson title.

2. Data source : course metadata collection of the vector store.

3. Update the system prompt in @backend/ai_generator so that the course title, course link, the number and the title of each lesson are all returned to address and outline related queries.

4. Make sure that the new tool is registered in the system."


## Testing and Debugging

(Shift+Tab)*2 for plan mode
"Think a lot" = extended thinking mode in Claude

Prompt = 
"The RAG chatbot returns query failed for any content related questions. I need you to:
1. write tests to evaluate the outputs of the execute method of the course search tool in @backend/search_tools.py
2. Write tests to evaluate if @backend/ai_generator.py correctly calls for the CourseSearchTool
3. Write tests to evaluate how the RAG system is handling the content query related questions.

Save the tests in a test folder within at backend. Run those tests against the current system to identify which components are failing. proposed fixes based on what the test reveal is broken. Think a lot."


## Working on many features in parallel and ensuring we dont duplicate

Make your own custom command= 

- create implement-feature.md
- if arguments to pass to custom command use `$`. eg, `$ARGUMENTS`
- something applied to every instamce = use CLAUDE.md
- use specific commands that you may or may not use across different conversations

`/permissions` on Claude code CLI
OR 
settings.local.json = set permissions and deny


## Worktrees

Work in parallel with claude code

- create copies of the codebase
- operate in isolation
- merge them together

`mkdir .trees`

`git worktree add folder/name_of_worktree`

create ui feature, testing feature and quality feature 
- git worktree add .trees/ui_feature
- git worktree add .trees/testing_feature
- git worktree add .trees/quality_feature


- open claude for each env
- run claude code in parallel
- ensures that if same files are modified, we dont overwrite 
- fix that when merging trees

WINDOW 1 = UI FEATURE
```
/implement-feature Toggle button design 
- Create a toggle button that fits the existing design aesthetic.  
- Position it in the top right.
- Use an icon based design (Sun/moon icons or similar)
- Smooth transition animation when toggling.
- Button should be accessible and keyboard navigable.
```

WINDOW 2 = TESTING FEATURE
```
Enhance the existing testing framework for the RAG system in @backend/tests.
The current tests cover unit components but are missing essential API testing infrastructure:

1. API Endpoint tests                                     
2. Test the fast API endpoints (/api/query, /api/courses, /) for proper request/response handling     
3. PyTest configuration                                   
4. Add pytest.ini_options in pyproject.toml for cleaner test execution.            5. Test fixtures                                          
6. create conftest.py with shared fixtures for mocking and test data setup.
The fast app in @backend/app.py mounts static files       
that don't exist in the test environment.                 
Either create a separate test app or define the API       
endpoints in line in the test file to avoid import issues.       
```

WINDOW 3 = QUALITY FEATURE
```
Add essential code quality tools to the development 
workflow. Set up black for automatic code formatting.
Add proper formatting consistency throughout the code base
and create development scripts for running quality checks.
```


## Phase 1: Worktrees Already Existed (created by Claude Code)

Claude Code (running mistral-nemo via Ollama) created three worktrees but failed to make any actual changes — all three branches were identical to main. 
We verified that:
`# Check each worktree has zero changes vs main
git -C .trees/quality_feature diff main --stat    # → empty
git -C .trees/testing_feature diff main --stat     # → empty
git -C .trees/ui_feature diff main --stat          # → empty`

`git push origin quality_feature`

`git push origin testing_feature`

`git push origin ui_feature`

