```mermaid
%%{init: { 'theme': 'base', 'themeVariables': { 'background': '#ffffff', 'primaryColor': '#ffffff', 'primaryBorderColor': '#7C0A02', 'lineColor': '#F5B841' } } }%%
flowchart TD
    A[Customer Initiates Contact] --> B{"AI Agent Identifies Issue"}
    
    %% Main Paths
    B -->|Card Misplaced| C[Temporary Lock Option]
    B -->|Card Lost/Stolen| D[Cancellation & Replacement]
    B -->|Card Damaged| E[Replacement While Using Current]
    B -->|Card Expiring| F[Explain Auto-Replacement]
    B -->|Card Expired, No Replacement| G[Urgent Replacement]
    
    %% Misplaced Card Path
    C --> C1{"Digital Wallet Access?"}
    C1 -->|Yes| C2[Explain Digital Wallet Use]
    C1 -->|No| C3[Explain Temporary Solutions]
    C2 --> C4{"Channel Preference?"}
    C3 --> C4
    C4 -->|App| C5[Guide CommBank App Lock Process]
    C4 -->|NetBank| C6[Guide NetBank Lock Process]
    C5 --> C7[Confirm Lock Applied]
    C6 --> C7
    C7 --> C8{"Card Found?"}
    C8 -->|Yes| C9[Guide Unlock Process]
    C8 -->|No| D
    
    %% Lost/Stolen Path
    D --> D1[Fraud Risk Assessment]
    D1 --> D2{"Suspicious Transactions?"}
    D2 -->|Yes| D3[Initiate Dispute Process]
    D2 -->|No| D4[Continue Replacement]
    D3 --> D4
    D4 --> D5{"Channel Preference?"}
    D5 -->|App| D6[Guide CommBank App Cancellation]
    D5 -->|NetBank| D7[Guide NetBank Cancellation]
    D6 --> D8[Confirm Replacement Order]
    D7 --> D8
    D8 --> D9[Address Verification]
    D9 --> X[Explain Next Steps]
    
    %% Damaged Card Path
    E --> E1{"Current Card Usable?"}
    E1 -->|Yes| E2[Explain Continued Use]
    E1 -->|No| E3[Offer Temporary Solutions]
    E2 --> E4{"Channel Preference?"}
    E3 --> E4
    E4 -->|App| E5[Guide CommBank App Replacement]
    E4 -->|NetBank| E6[Guide NetBank Replacement]
    E5 --> E7[Confirm Replacement Order]
    E6 --> E7
    E7 --> X
    
    %% Expiring Card Path
    F --> F1[Check Expected Delivery Timeframe]
    F1 --> F2{"Within 2-4 Weeks of Expiry?"}
    F2 -->|Yes| F3[Explain Standard Process]
    F2 -->|No| G
    F3 --> F4[Discuss Digital Wallet Continuity]
    F4 --> X
    
    %% Expired, No Replacement Path
    G --> G1[Urgent Resolution Options]
    G1 --> G2{"Location?"}
    G2 -->|Australia| G3[Branch Visit or Call Options]
    G2 -->|Overseas| G4[International Support Options]
    G3 --> X
    G4 --> X
    
    %% Next Steps
    X --> X1[Explain Interim Access Options]
    X1 --> X2[Detail Cardless Cash Option]
    X2 --> X3[Explain StepPay Option]
    X3 --> X4[Regular Payment Updates]
    X4 --> X5[Digital Wallet Updates]
    X5 --> Y[Offer Additional Assistance]
    
    %% Final Check
    Y --> Z{"Further Questions?"}
    Z -->|Yes| B
    Z -->|No| ZZ[End Conversation]
    
    style A fill:#FFFCEB,stroke:#F5B841,stroke-width:2px,color:#7C0A02
    style B fill:#FFCC29,stroke:#F5B841,stroke-width:1px,color:#000000
    style C fill:#FFFCEB,stroke:#F5B841,stroke-width:1px,color:#000000
    style D fill:#FFFCEB,stroke:#F5B841,stroke-width:1px,color:#000000
    style E fill:#FFFCEB,stroke:#F5B841,stroke-width:1px,color:#000000
    style F fill:#FFFCEB,stroke:#F5B841,stroke-width:1px,color:#000000
    style G fill:#FFFCEB,stroke:#F5B841,stroke-width:1px,color:#000000
    
    style C1 fill:#FFCC29,stroke:#F5B841,stroke-width:1px,color:#000000
    style C4 fill:#FFCC29,stroke:#F5B841,stroke-width:1px,color:#000000
    style C8 fill:#FFCC29,stroke:#F5B841,stroke-width:1px,color:#000000
    style D2 fill:#FFCC29,stroke:#F5B841,stroke-width:1px,color:#000000
    style D5 fill:#FFCC29,stroke:#F5B841,stroke-width:1px,color:#000000
    style E1 fill:#FFCC29,stroke:#F5B841,stroke-width:1px,color:#000000
    style E4 fill:#FFCC29,stroke:#F5B841,stroke-width:1px,color:#000000
    style F2 fill:#FFCC29,stroke:#F5B841,stroke-width:1px,color:#000000
    style G2 fill:#FFCC29,stroke:#F5B841,stroke-width:1px,color:#000000
    style Z fill:#FFCC29,stroke:#F5B841,stroke-width:1px,color:#000000
    
    style C2 fill:#E8F6FF,stroke:#4B77BE,stroke-width:1px,color:#4B77BE
    style C3 fill:#E8F6FF,stroke:#4B77BE,stroke-width:1px,color:#4B77BE
    style C5 fill:#E8F6FF,stroke:#4B77BE,stroke-width:1px,color:#4B77BE
    style C6 fill:#E8F6FF,stroke:#4B77BE,stroke-width:1px,color:#4B77BE
    style C9 fill:#E8F6FF,stroke:#4B77BE,stroke-width:1px,color:#4B77BE
    style D6 fill:#E8F6FF,stroke:#4B77BE,stroke-width:1px,color:#4B77BE
    style D7 fill:#E8F6FF,stroke:#4B77BE,stroke-width:1px,color:#4B77BE
    style E5 fill:#E8F6FF,stroke:#4B77BE,stroke-width:1px,color:#4B77BE
    style E6 fill:#E8F6FF,stroke:#4B77BE,stroke-width:1px,color:#4B77BE
    style F3 fill:#E8F6FF,stroke:#4B77BE,stroke-width:1px,color:#4B77BE
    style F4 fill:#E8F6FF,stroke:#4B77BE,stroke-width:1px,color:#4B77BE
    style G3 fill:#E8F6FF,stroke:#4B77BE,stroke-width:1px,color:#4B77BE
    style G4 fill:#E8F6FF,stroke:#4B77BE,stroke-width:1px,color:#4B77BE
    
    style D1 fill:#FFE8E8,stroke:#7C0A02,stroke-width:1px,color:#7C0A02
    style D3 fill:#FFE8E8,stroke:#7C0A02,stroke-width:1px,color:#7C0A02
    
    style E2 fill:#E8FFE8,stroke:#2E8B57,stroke-width:1px,color:#2E8B57
    style E3 fill:#E8FFE8,stroke:#2E8B57,stroke-width:1px,color:#2E8B57
    style X1 fill:#E8FFE8,stroke:#2E8B57,stroke-width:1px,color:#2E8B57
    style X2 fill:#E8FFE8,stroke:#2E8B57,stroke-width:1px,color:#2E8B57
    style X3 fill:#E8FFE8,stroke:#2E8B57,stroke-width:1px,color:#2E8B57
    style X4 fill:#E8FFE8,stroke:#2E8B57,stroke-width:1px,color:#2E8B57
    style X5 fill:#E8FFE8,stroke:#2E8B57,stroke-width:1px,color:#2E8B57
    
    style C7 fill:#F5F5F5,stroke:#333333,stroke-width:1px,color:#333333
    style D4 fill:#F5F5F5,stroke:#333333,stroke-width:1px,color:#333333
    style D8 fill:#F5F5F5,stroke:#333333,stroke-width:1px,color:#333333
    style D9 fill:#F5F5F5,stroke:#333333,stroke-width:1px,color:#333333
    style E7 fill:#F5F5F5,stroke:#333333,stroke-width:1px,color:#333333
    style X fill:#F5F5F5,stroke:#333333,stroke-width:1px,color:#333333
    style Y fill:#F5F5F5,stroke:#333333,stroke-width:1px,color:#333333
    style ZZ fill:#F5F5F5,stroke:#333333,stroke-width:1px,color:#333333
