# Smartphone-Based-Breast-Cancer-Screening-System-with-Thermal-Imaging-and-Microscopic-Analysis

flowchart TD
    Start([App Launch]) --> Login{User Login}
    Login -->|New User| Register[Registration Form]
    Register --> Verify[Verify Email/Phone]
    Verify --> Profile[Complete Medical Profile]
    Profile --> Dashboard
    Login -->|Existing User| Dashboard[Main Dashboard]
    
    Dashboard --> Setup[Setup Instructions]
    Setup --> DeviceCheck{Check Device Setup}
    
    DeviceCheck -->|Issue Found| Troubleshoot[Troubleshooting Guide]
    Troubleshoot --> DeviceCheck
    
    DeviceCheck -->|All Clear| SelectMode{Select Imaging Mode}
    
    SelectMode -->|Thermal| ThermalPrep[Thermal Imaging Preparation]
    SelectMode -->|Microscopic| MicroPrep[Microscopic Preparation]
    
    ThermalPrep --> ThermalGuide[Position Guide]
    ThermalGuide --> ThermalCheck{Environment Check}
    ThermalCheck -->|Unsuitable| ThermalAdjust[Adjustment Instructions]
    ThermalAdjust --> ThermalCheck
    ThermalCheck -->|Suitable| ThermalCapture[Capture Thermal Image]
    
    MicroPrep --> MicroGuide[Sample Preparation Guide]
    MicroGuide --> MicroCheck{Sample Quality Check}
    MicroCheck -->|Poor Quality| MicroAdjust[Adjustment Instructions]
    MicroAdjust --> MicroCheck
    MicroCheck -->|Good Quality| MicroCapture[Capture Microscopic Image]
    
    ThermalCapture & MicroCapture --> QualityCheck{Image Quality Check}
    QualityCheck -->|Poor Quality| Retake[Retake Instructions]
    Retake --> SelectMode
    
    QualityCheck -->|Good Quality| Processing[Image Processing]
    Processing --> MLAnalysis[ML Model Analysis]
    
    MLAnalysis --> ResultsCheck{Analysis Complete}
    ResultsCheck -->|Error| ErrorHandle[Error Handling]
    ErrorHandle --> Dashboard
    
    ResultsCheck -->|Success| Results[Results Display]
    Results --> DetailedAnalysis[Detailed Analysis]
    
    DetailedAnalysis --> Risk{Risk Level}
    Risk -->|Low| SafeReport[Generate Safety Report]
    Risk -->|Medium| RecConsult[Recommend Consultation]
    Risk -->|High| UrgentConsult[Urgent Medical Attention]
    
    SafeReport & RecConsult & UrgentConsult --> SaveResults[Save Results]
    SaveResults --> Share{Share Options}
    
    Share -->|Doctor| DoctorShare[Share with Healthcare Provider]
    Share -->|Download| Download[Download Report]
    Share -->|Skip| Skip[Skip Sharing]
    
    DoctorShare & Download & Skip --> Schedule{Schedule Follow-up}
    Schedule -->|Yes| Reminder[Set Reminder]
    Schedule -->|No| End
    
    Reminder --> End([Return to Dashboard])

    subgraph Legend
        direction LR
        UserAction[User Action]
        SystemCheck{System Check}
        Processing[Processing Step]
        Decision{Decision Point}
    end
