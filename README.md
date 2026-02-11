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

