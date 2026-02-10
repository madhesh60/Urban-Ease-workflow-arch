```mermaid
graph TD
    subgraph Frontend["Frontend Layer (Presentation)"]
        UI[UI Module<br/>Multilingual screens, forms, voice I/O]
        Auth[Authentication Module<br/>DigiLocker login, OTP/biometrics]
        Select[Service Selection Module<br/>Options for complaints, tracking, queues]
        Upload[Upload & Preview Module<br/>Photos/docs handling]
        Feedback[Feedback & Receipt Module<br/>Status display, printing]
    end

    subgraph Backend["Backend Layer (Business Logic)"]
        Gateway[API Gateway Module<br/>Routing, auth checks]
        Process[Request Processing Module<br/>Validation, routing]
        Track[Status Tracking Module<br/>Real-time updates, history]
        Notify[Notification Module<br/>SMS/WhatsApp reminders]
        Escalate[Emergency Escalation Module<br/>Crisis triggers]
    end

    subgraph AI["AI Layer (Intelligent Features)"]
        Visual[Visual Detection Module<br/>Photo analysis, categorization]
        Voice[Voice Interaction Module<br/>Speech-to-text, responses]
        Crisis[Crisis Response Agent Module<br/>Reasoning, geo-alerts]
        Predict[Predictive Analytics Module<br/>ETAs, queue predictions]
    end

    subgraph Data["Data Layer (Storage)"]
        UserData[User Data Module<br/>Session info, DPDP compliance]
        History[Request History Module<br/>Complaints, resolutions]
        Analytics[Analytics Data Module<br/>Historical data for AI]
    end

    subgraph External["External Integrations Layer"]
        Digi[DigiLocker Integration<br/>Doc verification]
        Utils[Utility APIs<br/>Electricity/Gas/Water Depts]
        NotifProv[Notification Providers<br/>SMS/WhatsApp APIs]
        Emerg[Emergency Services<br/>Fire/Medical APIs]
    end

    %% Interactions
    Frontend -->|API Calls| Backend
    Backend -->|Queries/Tools| AI
    Backend <-->|Store/Retrieve| Data
    Backend -->|Integrate| External
    AI -->|Data Insights| Data

    %% Styling
    classDef layer fill:#f0f0f0,stroke:#333,stroke-width:2px,color:#000
    class Frontend,Backend,AI,Data,External layer
    ```
